<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-white customnav" @mouseenter="isHovering = true">
  <div class="container-fluid">
    <a class="navbar-brand me-5" href="#"><img src="../assets/logo.png" alt="" width="250px"></a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <img src="../assets/menu.svg" alt="">
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <input class="form-control me-5 bg-light" type="search" placeholder="Поиск по сайту.." aria-label="Search">
        <button class="btn btn-outline-dark col-2 me-3 custom" type="submit">Обратный звонок</button>
        <button class="btn btn-outline-dark custom" type="submit"><img src="../assets/user.svg" alt="" srcset=""></button>
    </div>
  </div>
</nav>
<nav class="navbar navbar-expand-lg navbar-light bg-white" :class="[ isHovering ? 'scrolled' : 'scrollDown']" ref="headRef" @mouseleave="isHovering = false">
  <div class="container-fluid">
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link" href="#">Направления</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Специалисты</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Предложения</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Клиники</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Аппараты</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Пациентам</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Новости и медиа</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">О клинике</a>
        </li>
        <div class="feed">
          <button class="btn btn-outline-dark feedback" type="submit">Обратный звонок</button>
          <button class="btn btn-outline-dark feedback" type="submit"><img src="../assets/user.svg" alt="" srcset=""></button>
        </div>
      </ul>
    </div>
  </div>
</nav>
</template>

<script>
export default {
  data() {
    return {
      isHovering: false
    }
  },
   methods: {
      kek() {
        if (isHovering) {

        }
      },
      vueOnScroll() {
        var prev = window.pageYOffset
        const refs = this.$refs.headRef
        window.addEventListener("scroll", () => {
          var curr = window.pageYOffset
          if (prev > curr) {
            refs.classList.add("scrolled")
            refs.classList.remove("scrollDown")
          } else {
            refs.classList.add("scrollDown")
            refs.classList.remove("scrolled")
          }
          if (curr === 0) {
            refs.classList.remove("scrollDown")
            refs.classList.remove("scrolled")
          }
            prev = curr;
        });
      },
    },
    mounted() {
      this.vueOnScroll()
    }
}
</script>

<style scoped>

.customnav {
  position: sticky;
  top: 0;
  z-index: 1000;
}

@media (max-width: 992px) {
  .custom {
    display: none;
  }
}

@media (max-width: 992px) {
  .feedback {
    display: block !important;
  }
}

.feed {
  display: flex;
  flex-direction: row;
  gap: 15px;
}

.feedback {
    display: none;
  }

.navbar-nav {
  align-items:flex-start ;
}
.navbar-toggler {
  border: none;
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}

.scrolled {
        position: sticky;
        top: 60px;
        animation: 0.3s show ease-in-out;
    }
    .scrollDown {
        position: sticky;
        animation: 0.3s hide ease-in-out;
    }
    @keyframes show {
    from {
        top: 0px;
    }
    to {
        top: 60px;
        }
    }
    @keyframes hide {
    from {
        top: 60px;
    }
    to {
        top: 0px;
    
        }
    }
</style>
