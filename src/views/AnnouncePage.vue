<script setup>
import { onBeforeMount, ref } from 'vue';
// import { apiGetAnnounce } from '@/api/index.js';

const isAnnounceLoaded = ref(false);
const announceData = ref([]);
const currentPage = ref(1);
// const currentDate = new Date();

// onBeforeMount(() => {
//     apiGetAnnounce()
//         .then((response) => {
//             switch (response.status) {
//                 case 200:
//                     const announceRows = response.data.datas;
//                     if (response.data.datas == '') {
//                         announceData.value = [];
//                         isAnnounceLoaded.value = true;
//                     } else {
//                         const selectedRows = announceRows.filter((row) => {
//                             const startDate = new Date(
//                                 formatDate(row.BAS08004)
//                             );
//                             const endDate = new Date(formatDate(row.BAS08005));
//                             return (
//                                 currentDate > startDate && currentDate < endDate
//                             );
//                         });
//                         announceData.value = selectedRows;
//                         isAnnounceLoaded.value = true;
//                     }
//                     break;
//             }
//         })
//         .catch((error) => {
//             console.log(error);
//             switch (error.response.status) {
//                 case 500:
//                     alert(
//                         '系統異常請聯絡系統管理員，錯誤資訊: ' +
//                             error.response.data.datas
//                     );
//                     break;
//             }
//         });
// });

// const formatDate = (date) => {
//     return date.slice(0, 4) + '/' + date.slice(4, 6) + '/' + date.slice(6, 8);
// };
</script>

<template>
    <v-container class="h-100" fluid>
        <v-row
            justify="center"
            class="my-1 text-lg-h1 text-md-h2 text-h3 font-weight-black"
        >
            最新消息
        </v-row>
        <v-row justify="center">
            <v-card width="90vw" elevation="3" class="mx-2">
                <v-table class="bg-grey-lighten-5" height="100%">
                    <thead>
                        <tr>
                            <th
                                class="pa-3 text-center text-lg-h2 text-md-h3 text-h4 font-weight-black bg-blue-darken-4"
                                style="width: 20%"
                            >
                                標題
                            </th>
                            <th
                                class="pa-3 text-center text-lg-h2 text-md-h3 text-h4 font-weight-black bg-blue-darken-4"
                            >
                                內容
                            </th>
                            <th
                                class="pa-3 text-center text-lg-h2 text-md-h3 text-h4 font-weight-black bg-blue-darken-4"
                                style="width: 20%"
                            >
                                日期
                            </th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr
                            v-if="!isAnnounceLoaded"
                            class="text-h4 pa-3 text-center"
                        >
                            資料載入中...
                        </tr>
                        <tr
                            v-for="(row, index) in announceData"
                            v-else
                            :key="index"
                            class="text-subtitle-1"
                        >
                            <td class="text-center text-h4 pa-3">
                                {{ row['BAS08002'] }}
                            </td>
                            <td class="text-h4 pa-3">
                                {{ row['BAS08003'] }}
                            </td>
                            <td class="text-center text-h4 pa-3">
                                {{ formatDate(row['BAS08004']) }}
                            </td>
                        </tr>
                    </tbody>
                </v-table>
                <v-container
                    v-if="announceData.length == 0"
                    class="text-h4 pa-3 text-center flex-grow-1"
                    style="width: 100%"
                >
                    今日無有效公告資訊
                </v-container>
            </v-card>
        </v-row>
        <v-row justify="center">
            <v-pagination
                v-show="announceData.length > 0"
                v-model="currentPage"
                :length="Math.ceil(announceData.length / 3)"
                :per-page="2"
                :total-visible="3"
                rounded="circle"
            >
            </v-pagination>
        </v-row>
    </v-container>
</template>
