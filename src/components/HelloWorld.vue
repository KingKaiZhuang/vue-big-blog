<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello {
  width: 100%;
  height: 500px;
  background-image: url('https://i.ytimg.com/vi/_SiCRVuw38s/maxresdefault.jpg');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  background-color: #000;
  position: relative;

  h1 {
    width: 100%;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    color: #fff;
    font-size: 80px;
    z-index: 10;
  }
}
.hello::after {
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background-color: #00000061;
}

</style>
