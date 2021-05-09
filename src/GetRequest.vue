<template>
  <div class="d-flex flex-column mx-5 my-2">
    <div class="alert alert-primary alert-dismissible fade show" role="alert">
      Valor BitCoin hoje: <strong>R$ {{ valorCompra }}</strong>
      <br />
      <small
        >valor do BitCoin extraído de:
        https://www.blockchain.com/pt/api/exchange_rates_api</small
      >
    </div>
    <form class="d-flex flex-row">
      <div class="form-group w-50 p-3 text-left">
        <label for="real">Valor em Real</label>
        <br />
        <input
          v-model.number="valorReal"
          id="real"
          type="number"
          class="form-control"
          placeholder="R$ 0.00"
          aria-describedby="realHelp"
        />
        <p>
          Conversão para BitCoins:
          <span class="badge badge-secondary"
            >BTC {{ valorReal * valorCompra }}</span
          >
        </p>
      </div>
      <div class="form-group w-50 p-3 text-left">
        <label for="btc">Valor em BitCoin</label>
        <input
          v-model.number="ValorBtc"
          id="real"
          type="number"
          class="form-control"
          placeholder="R$ 0.00"
          aria-describedby="realHelp"
        />
        <p>
          Conversão para Real:
          <span class="badge badge-secondary"
            >R$ {{ ValorBtc / valorCompra }}</span
          >
        </p>
      </div>
    </form>
    <div class="text-left">
      <small>
        Atividade Prévia - Trabalho Prático | REA - Desenvolvimento Reativo<br />
        Aluno: Matheus Alexandre de Souza Cometti</small
      >
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "get-request",
  data() {
    return {
      valorCompra: null,
      valorReal: 0,
      ValorBtc: 0,
      message: "",
    };
  },
  methods: {
    changeReal: function() {
      console.log("entrou aqui");
    },
  },

  created() {
    // Simple GET request using axios
    axios
      .get("https://blockchain.info/tobtc?currency=BRL&value=1")
      .then((response) => (this.valorCompra = response.data));
  },
};
</script>
