<template>
  <header class="wrapper bg-light text-primary">
    <nav
      :class="`navbar navbar-expand-lg center-nav transparent position-absolute  ${
        addClass2 ? 'fixed navbar-clone' : ''
      } ${
        addClass
          ? 'navbar-clone navbar-stick navbar-light'
          : ' navbar-unstick navbar-dark'
      } `"
    >
      <div class="container flex-lg-row flex-nowrap align-items-center">
        <div class="navbar-brand w-100">
          <nuxt-link to="/">
            <HeadersHeader-Logo />
          </nuxt-link>
        </div>
        <div
          class="navbar-collapse offcanvas offcanvas-nav offcanvas-start"
          id="ofCanvasBody"
        >
          <div class="offcanvas-header d-lg-none">
            <h3 class="text-white fs-30 mb-0">Tech Renuka</h3>
            <button
              type="button"
              class="btn-close btn-close-white"
              data-bs-dismiss="offcanvas"
              @click="menuClose"
              aria-label="Close"
            ></button>
          </div>
          <div class="offcanvas-body ms-lg-auto d-flex flex-column h-100">
            <ul class="navbar-nav">
              <HeadersComponentsMenu />
            </ul>
            <!-- /.navbar-nav -->
            <div class="offcanvas-footer d-lg-none">
              <div>
                <a href="mailto:contact@techrenuka.com" class="link-inverse"
                  >contact@techrenuka.com</a
                >
                <br />
                +91-80000-78982 <br />
                <nav class="nav social social-white mt-4">
                  <HeadersComponentsSocials />
                </nav>
                <!-- /.social -->
              </div>
            </div>
            <!-- /.offcanvas-footer -->
          </div>
          <!-- /.offcanvas-body -->
        </div>
        <!-- /.navbar-collapse -->
        <div class="navbar-other w-100 d-flex ms-auto">
          <ul class="navbar-nav flex-row align-items-center ms-auto">
            <!-- <li class="nav-item dropdown language-select text-uppercase">
              <HeadersComponentsLanguage />
            </li> -->
            <li class="nav-item d-none d-md-block">
              <nuxt-link to="/contact" class="btn btn-sm btn-white rounded-pill"
                >Contact</nuxt-link
              >
            </li>
            <li class="nav-item d-lg-none">
              <button class="hamburger offcanvas-nav-btn" @click="menuOpen">
                <span></span>
              </button>
            </li>
          </ul>
          <!-- /.navbar-nav -->
        </div>
        <!-- /.navbar-other -->
        <div
          id="offcanvasBackdrop"
          @click="menuClose"
          class="offcanvas-backdrop fade"
          style="display: none"
        ></div>
      </div>
      <!-- /.container -->
    </nav>
    <!-- /.navbar -->
  </header>
</template>
<script setup>
const menuOpen = () => {
  document.getElementById("ofCanvasBody").classList.toggle("show");
  document.getElementById("offcanvasBackdrop").style.display = "block";
  document.getElementById("offcanvasBackdrop").classList.toggle("show");
};

const menuClose = () => {
  document.getElementById("ofCanvasBody").classList.toggle("show");
  document.getElementById("offcanvasBackdrop").classList.toggle("show");
  setTimeout(() => {
    document.getElementById("offcanvasBackdrop").style.display = "none";
  }, 300);
};

const addClass = ref(false);
const addClass2 = ref(false);

const handleScroll = () => {
  addClass2.value = window.scrollY >= 200;
  addClass.value = window.scrollY >= 300;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style lang="scss" scoped></style>
