<template>
  <section class="sponsors">
    <h2 class="title">Спонсоры и члены ассоциации</h2>

    <div class="grid">
      <div
        v-for="(logo, index) in logos"
        :key="index"
        class="logo-item"
      >
        <img :src="logo" alt="sponsor logo" />
      </div>
    </div>
  </section>
</template>

<script setup>
import boggart from '@/assets/sponsors/boggart.png'
import dmt from '@/assets/sponsors/dmtlogo.png'
import opensolutions from '@/assets/sponsors/opensolutions.png'
import infotecs from '@/assets/sponsors/infotecs.png'
import elsoft from '@/assets/sponsors/elsoft.png'
import rubin from '@/assets/sponsors/rubin.png'
import reliable from '@/assets/sponsors/reliable.png'
import okdesk from '@/assets/sponsors/okdesk.png'
import arvr from '@/assets/sponsors/arvr3d.png'
import secon from '@/assets/sponsors/secon.png'
import tortuga from '@/assets/sponsors/tortuga.png'

// Добавь или убери лого — сетка подстроится автоматически
const logos = [
  boggart,
  dmt,
  opensolutions,
  infotecs,
  elsoft,
  rubin,
  reliable,
  okdesk,
  arvr,
  secon,
  tortuga
]
</script>

<style scoped>
.sponsors {
  margin-top: 120px;
  padding: 0 126px 80px 126px;
  text-align: center;
  color: white;
}

.title {
  font-size: 32px;
  font-weight: 700;
  margin-bottom: 60px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 40px 60px;
  align-items: center;
  justify-items: center;
}

.logo-item img {
  width: 100%;
  max-width: 180px;
  opacity: 0.9;
  transition: 0.25s ease;
}

.logo-item img:hover {
  opacity: 1;
  transform: scale(1.06);
}

/* ---------- Адаптив ---------- */

@media (max-width: 1200px) {
  .grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
  }
}

@media (max-width: 768px) {
  .sponsors {
    padding: 0 40px 60px 40px;
  }

  .grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
  }

  .title {
    font-size: 26px;
  }
}

@media (max-width: 480px) {
  .sponsors {
    padding: 0 20px 40px 20px;
  }

  .grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
  }

  .logo-item img {
    max-width: 130px;
  }
}
</style>