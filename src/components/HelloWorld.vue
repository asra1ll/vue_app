<template>
  <v-card
    max-width="450"
    class="mx-auto mt-5"
  >
    <v-toolbar
      color="blue"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title></v-toolbar-title>

      <v-text-field
            placeholder="검색"
            hide-details
          ></v-text-field>

      <v-btn icon>
        <v-icon @click="overlayTest">mdi-magnify</v-icon>
      </v-btn>
    </v-toolbar>

    <v-list three-line>
      <template v-for="(item, index) in items">
        <v-subheader
          class=""
          v-if="item.header"
          :key="item.header"
          v-text="item.header"
        ></v-subheader>

        <v-divider
          v-else-if="item.divider"
          :key="index"
          :inset="item.inset"
        ></v-divider>

        <v-list-item
          v-else
          :key="item.title"
          
        >
          <v-list-item-avatar @click="test(item.avatar)">
            <v-img :src="item.avatar"></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title v-html="item.title"></v-list-item-title>
            <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>
    </v-list>
    <template>
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          Privacy Policy
        </v-card-title>

        <v-img :src="imgURL"></v-img>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            I accept
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    </template>
  </v-card>
  
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
      label: "眞夫必見書(진부필견서)",
      imgURL: null,
      dialog: false,
      items: [
        { header: '상남자의 기본 자질' },
        {
          avatar: require('../assets/images/1.jpg'),
          title: '첫번째 자질 <span class="red--text text--lighten-1">1</span>',
          subtitle: "<span class='text--primary'>용맹</span> &mdash; 상남자는 용맹하게 적에게 달려들어 그들을 죽여야 한다.",
        },
        { divider: true, inset: true },
        {
          avatar: require('../assets/images/2.jpg'),
          title: '두번째 자질 <span class="red--text text--lighten-1">2</span>',
          subtitle: "<span class='text--primary'>침착</span> &mdash; 상남자는 그 어느 때에도 침착하게 적을 상대할 줄 알아야 한다.",
        },
        { divider: true, inset: true },
        {
          avatar: require('../assets/images/3.jpg'),
          title: '세번째 자질 <span class="red--text text--lighten-1">3</span>',
          subtitle: "<span class='text--primary'>관용</span> &mdash; 상남자는 아군이 잘못했을 때, 상대방이 죽기살기로 도망칠 때 한번은 용서해주어야 한다.",
        },
        { divider: true, inset: true },
        {
          avatar: require('../assets/images/4.jpg'),
          title: '네번째 자질 <span class="red--text text--lighten-1">4</span>',
          subtitle: "<span class='text--primary'>대화</span> &mdash; 상남자는 다짜고짜 죽이는 것이 아닌 대화를 통해 풀고, 어쩔 수 없을 때 적을 죽여야 한다.",
        },
        { divider: true, inset: true },
        {
          avatar: require('../assets/images/5.jpg'),
          title: '다섯번째 자질 <span class="red--text text--lighten-1">5</span>',
          subtitle: "<span class='text--primary'>교양</span> &mdash; 상남자는 교양이 있어야한다. 교양없는 상남자는 양아치와 다름이 없기 때문이다.",
        },
        { divider: true, inset: true },
        {
          avatar: require('../assets/images/6.jpg'),
          title: '여섯번째 자질 <span class="red--text text--lighten-1">6</span>',
          subtitle: "<span class='text--primary'>globalization</span> &mdash; 상남자는 세계적이여야한다. 이 나라는 너무나도 좁기에 우리는 공허하고 세계와 소통해야한다.",
        },
        { divider: true, inset: true },
        {
          avatar: require('../assets/images/7.jpg'),
          title: '일곱번째 자질 <span class="red--text text--lighten-1">7</span>',
          subtitle: "<span class='text--primary'>포부</span> &mdash; 상남자는 솔킬만을 바라보지 않는다. 게임의 승리를 위한 포부가 있어야하고 솔킬은 그 과정에 불과하다.",
        },
        { divider: true, inset: true },
        {
          avatar: require('../assets/images/8.jpg'),
          title: '여덟번째 자질 <span class="red--text text--lighten-1">8</span>',
          subtitle: "<span class='text--primary'>의지(必)</span> &mdash; 마음 심(心)자에 신념의 막대기를 꽂으면 반드시 필(必)- 열역학의 거장, 마에스트로 -웅산- 교수님 8대 자질중 가장 중요한 마지막 자질로 앞서 말한 7가지 자질을 실천할 때에도 의지가 필요하기에 가장 중요한 자질이다. 이 8번째 자질만 있다면 사나이력(力)은 이루 말할 수 없을 정도로 강해진다고 한다.",
        },
      ],
    }),
    methods: {
      test(url){
        this.imgURL=url;
        this.dialog=true;
      },
      overlayTest(){
        
      }
    }
  }
</script>


