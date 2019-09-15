<template>
    <div>
        <div>
            <v-breadcrumbs :items="items">
                <template v-slot:item="props">
                <v-breadcrumbs-item
                    :href="props.item.href"
                    :class="[props.item.disabled && 'disabled']"
                >
                    {{ props.item.text.toUpperCase() }}
                </v-breadcrumbs-item>
                </template>
            </v-breadcrumbs>
        </div>
        <div>
            <v-data-table
                :headers="headers"
                :items="desserts"
                :expanded.sync="expanded"
                item-key="name"
                show-expand
                class="elevation-1"
            >
                <template v-slot:top>
                <v-toolbar flat color="white">
                    <v-toolbar-title>ランキング</v-toolbar-title>
                    <div class="flex-grow-1"></div>
                </v-toolbar>
                </template>
                <template v-slot:expanded-item="{ headers }">
                <td :colspan="headers.length">Peek-a-boo!</td>
                </template>
            </v-data-table>
        </div>
    </div>
</template>

<script>
  export default {
    data: () => ({
      items: [
        {
          text: '個別ページ',
          disabled: false,
          href: '/contests/4',
        },
        {
          text: '投稿',
          disabled: false,
          href: '/contests/4/post',
        },
        {
          text: 'ランキング',
          disabled: true,
          href: '/contests/4/ranking',
        },
      ],
    }),
  }
</script>