<template>
  <div>
    <div>
      <v-menu
        ref="menu"
        v-model="menu"
        :close-on-content-click="false"
        transition="scale-transition"
        offset-y
        min-width="auto"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-text-field
            v-model="date"
            label="Birthday date"
            prepend-icon="mdi-calendar"
            readonly
            v-bind="attrs"
            v-on="on"
          ></v-text-field>
        </template>
        <v-date-picker
          v-model="date"
          :active-picker.sync="activePicker"
          :max="new Date().toISOString().substr(0, 10)"
          min="1950-01-01"
          @change="save"
        ></v-date-picker>
      </v-menu>
    </div>
    <div class="input-container">
    <div class="input-container-col">
      <v-text-field
        :v-model="data.rent"
        label="Аренда + коммунальные"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.net"
        label="Интернет"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.rubbish"
        label="Мусор"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.accountant"
        label="Бухгалтер"
        outlined
      ></v-text-field>
      <v-text-field :v-model="data.tax" label="Налоги" outlined></v-text-field>
      <v-text-field
        :v-model="data.security"
        label="Охрана"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.acquiring"
        label="Процент эквайлинга"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.salary"
        label="Заробатная плата"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.marketing"
        label="Маркетинг"
        outlined
      ></v-text-field>
    </div>
      <div class="input-container-col">
      <v-text-field
        :v-model="data.rent"
        label="Аренда + коммунальные"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.net"
        label="Интернет"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.rubbish"
        label="Мусор"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.accountant"
        label="Бухгалтер"
        outlined
      ></v-text-field>
      <v-text-field :v-model="data.tax" label="Налоги" outlined></v-text-field>
      <v-text-field
        :v-model="data.security"
        label="Охрана"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.acquiring"
        label="Процент эквайлинга"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.salary"
        label="Заробатная плата"
        outlined
      ></v-text-field>
      <v-text-field
        :v-model="data.marketing"
        label="Маркетинг"
        outlined
      ></v-text-field>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    activePicker: null,
    date: null,
    menu: false,
    data: {
      rent: 0,
      net: 0,
      rubbish: 0,
      accountant: 0,
      tax: 0,
      security: 0,
      acquiring: 0,
      salary: 0,
      marketing: 0,
    },
  }),
  watch: {
    menu(val) {
      val && setTimeout(() => (this.activePicker = "YEAR"));
    },
  },
  methods: {
    save(date) {
      this.$refs.menu.save(date);
    },
  },
};
</script>

<style lang="css" scoped>

.input-continer {
    display: flex;
}

.input-continer-col {
    width: 50%;
    padding: 20px;
}
</style>
