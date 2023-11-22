<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">進撃の巨人 愛好者</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav ms-auto">
          <router-link to="/" class="nav-link">首頁</router-link>
          <a class="nav-link" href="#">心得</a>
          <div class="btn-group">
            <button type="button" class="btn btn-outline-0 btn-transparent dropdown-toggle" data-bs-toggle="dropdown"
              aria-expanded="false">
              關於
            </button>
            <ul class="dropdown-menu dropdown-menu-end">
              <li><router-link to="/about/AttackOnTitan" class="nav-link">進擊的巨人</router-link></li>
            </ul>
          </div>
          
          <div class="btn-group">
            <button type="button" class="btn btn-outline-0 btn-transparent dropdown-toggle" data-bs-toggle="dropdown"
              data-bs-display="static" aria-expanded="false">
              帳號
            </button>
            <ul class="dropdown-menu dropdown-menu-end">
              <li><a class="dropdown-item" href="#">登入</a></li>
              <li><a class="dropdown-item" href="#">Menu item</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </nav>

  <router-view></router-view>
</template>

<style lang="scss">
@import "./assets/all.scss"
</style>
