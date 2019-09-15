<template>
  <v-layout>
    <v-flex class="text-center">
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
          <div>
            <v-card
              max-width="1344"
              class="mx-auto"
            >
            <v-card-title>問題文</v-card-title>
            <v-card-text>高橋君は 3 桁のパスワードを設定しようとしています。<br />使える文字が 1以上 N以下の数字のみであるとき、設定できるパスワードが全部で何種類であるかを答えてください。</v-card-text>
            </v-card>
          </div>
        </div>
    </v-flex>
  </v-layout>
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