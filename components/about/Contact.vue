<template>
  <section class="wrapper bg-light">
    <div class="container pt-12 pt-md-14 pb-10 pb-md-12">
      <div class="row gx-lg-8 gx-xl-12 gy-10 align-items-center">
        <div class="col-lg-7">
          <figure>
            <nuxt-img
              class="w-auto"
              src="/assets/img/illustrations/about-i5.webp"
              srcset="/assets/img/illustrations/about-i5.webp"
              alt="photo"
            />
          </figure>
        </div>
        <div class="col-lg-5">
          <h2
            class="fs-15 text-uppercase text-line text-primary text-center mb-3"
          >
            Get In Touch
          </h2>
          <h3 class="display-5 mb-7">
            Got any questions? Don't hesitate to get in touch.
          </h3>
          <div
            v-for="item in aboutContact"
            :key="item.id"
            class="d-flex flex-row"
          >
            <div>
              <div class="icon text-primary fs-28 me-6 mt-n1">
                <i :class="item.iconClass"></i>
              </div>
            </div>
            <div>
              <h5 class="mb-1">{{ item.title }}</h5>

              <address v-if="item.address">
                {{ item.address.line1 }}<br class="d-none d-md-block" />{{
                  item.address.line2
                }}
              </address>

              <p v-if="item.content">{{ item.content }}</p>
              <a v-if="item.mail" :href="item.mail" class="link-body">{{
                item.mail
              }}</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { aboutContact } from "~/data/contact";
</script>

<style lang="scss" scoped></style>
