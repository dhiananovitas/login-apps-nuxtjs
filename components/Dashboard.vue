<template>
  <v-row>
    <v-col
      v-for="board in cards"
      :key="board"
      cols="12"
    >
      <v-card>
        <v-subheader>{{ board }}</v-subheader>

        <v-list two-line>
          <template v-for="n in 12">
            <v-list-item

              :key="n"
            >
              <v-list-item-avatar color="grey darken-1" style="background-color: bisque;margin-right: 10px;">
              </v-list-item-avatar>

              <v-list-item-content>
                <v-list-item-title>Pegawai {{ n }}</v-list-item-title>

                <v-list-item-subtitle>
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil repellendus distinctio similique
                </v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-icon
              v-for="icon in icons"
              :key="icon"
              >
                <v-icon>{{ icon }}</v-icon>
              </v-list-item-icon>
            </v-list-item>

            <!-- <v-divider
              v-if="n !== 6"
              :key="`divider-${n}`"
              inset
            ></v-divider> -->
          </template>
        </v-list>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
    name: 'dasboard',
    data: () => ({
        cards: ['Data Pegawai'],
        icons: ['mdi-delete'],
    }),
}
</script>