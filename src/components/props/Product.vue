<script>
export default {
  name: "Product",
  props: {
    product: Object,
  },

  data() {
    return {
      result: {
        newPrice: "",
        sale: "",
        salePerc: "",
        sos: "",
      },
    };
  },

  methods: {
    getSale(badge) {
      let controlloDiscount = false;
      let controlloSostenibilita = false;
      this.result.sale = this.result.sos = "false";
      badge.forEach((element) => {
        // nuovo prezzo
        if (element.type === "discount") {
          controlloDiscount = true;
          console.log("ENTRA");
          this.result.sale = true;
          if (element.value.includes("-50%")) {
            this.result.newPrice = (this.product.price / 2).toFixed(2);
            this.result.salePerc = "-50%";
          } else {
            this.result.newPrice = (this.product.price * 0.7).toFixed(2);
            this.result.salePerc = "-30%";
          }
        } else {
          this.result.sale = false;
        }
      });

      // CICLO SOSTENIBILITA'
      badge.forEach((element) => {
        // sostenibilità
        if (element.type === "tag") {
          controlloSostenibilita = true;

          this.result.sos = true;
        } else {
          this.result.sos = false;
        }
      });

      if (controlloDiscount) {
        this.result.sale = true;
      } else {
        this.result.sale = false;
      }

      if (controlloSostenibilita) {
        this.result.sos = true;
      } else {
        this.result.sos = false;
      }
    },

    getImagePath(img) {
      return new URL(`../../assets/img/${img}`, import.meta.url).href;
    },
  },

  mounted() {
    this.getSale(this.product.badges);
  },

  computed() {},
};
</script>

<template>
  <div class="prodotto">
    <!-- img nascosta -->
    <img
      class="nascosta"
      :src="getImagePath(product.backImage)"
      :alt="product.name"
    />

    <!-- cuore -->
    <div class="cuore">
      <span>&hearts;</span>
    </div>
    <!-- BADGE -->
    <div class="badge">
      <div v-show="result.sale">
        <div class="sconto">{{ result.salePerc }}</div>
      </div>

      <div v-show="result.sos">
        <div class="sconto sosteni">Sostenibilitá</div>
      </div>
    </div>

    <!-- img in primo piano -->
    <img :src="getImagePath(product.frontImage)" :alt="product.name" />
    <span class="marca">{{ product.brand }}</span>
    <h4 class="nome">{{ product.name }}</h4>
    <span :class="{ 'marca prezzo': result.newPrice != '' }">{{
      result.newPrice
    }}</span>
    <span
      class="marca prezzo originale"
      :class="{ line: result.newPrice != '' }"
      >{{ product.price }}</span
    >
  </div>
</template>

<style lang="scss" scoped>
// @use "../assets/scss/partials/variables" as *;

/* hover */
// line-through
.line {
  text-decoration: line-through;
}
.prodotto {
  width: 410px;
  margin: 8px;
  position: relative;
  cursor: pointer;

  &:hover .nascosta {
    display: block;
  }
  & .nascosta {
    position: absolute;
    display: none;
    top: 0;
    right: 0;
  }
  & .cuore {
    position: absolute;
    top: 10px;
    left: 88%;
    padding: 5px 15px;

    font-size: 2rem;
    background-color: white;
    color: black;

    &:hover {
      color: red;
    }
  }
  .badge {
    position: absolute;
    bottom: 90px;
    left: 0;
    display: flex;
  }
  & .sconto {
    background-color: red;
    color: white;
    font-size: 0.8rem;
    padding: 5px 10px;
    margin-right: 6px;
    &.sosteni {
      background-color: green;
      // left: 50px;
    }
    &.sosteni.singolo {
      left: 0;
    }
  }
}

.marca {
  font-size: 0.8rem;
  padding-bottom: 0;
  &.prezzo {
    color: red;
    margin-right: 5px;
    &.originale {
      color: black;
      // text-decoration: line-through;
    }
    &::after {
      content: " \20AC";
    }
  }
}

.nome {
  text-transform: uppercase;
}
</style>
