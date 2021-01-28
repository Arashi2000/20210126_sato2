<template>
<div id="app">
<div class="home">
<input type="text" v-model="text"/>
<button class="button-side" @click="getAdress">住所自動入力</button>
</div>
<div class="text-area">
<p class="address">address:</p>
<!-- マスタッシュ記法でaddress変数の値を描画 -->
<p class="show-text">{{address}}</p>
</div>
</div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      text:"",
      let address = "Hello";// アドレス変数の定義をする
    };
  },
  methods: {
    async getAdress() {
      alert('関数が呼ばれたよ！');
      const item = await axios.get('https://apis.postcode-jp.com/api/v4/postcodes/text?apiKey=nfssvafHfXGWsplNuRMQjcmCXiqcGIMzinBeyEb');
      
      // this.adress = await this.$axios.$get('https://postcode-jp.com/');
      const getData = await axios.get('リクエストURL');
      console.log(getData); //値が受け取れているか確認

      this.address = //住所代入;
      // 受け取った値(getData)の中から住所を取得する際は以下教材の
      // 「オブジェクトへのアクセス」を参考に値を取り出してみてください！
      // https://coachtech-lms.com/javascript/javascript-object/2718/
    
    },
    sendAdress() {
      console.log("Hello");
    }
  }
};
</script>

<style>
html, body, div, span, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
abbr, address, cite, code,
del, dfn, em, img, ins, kbd, q, samp,
small, strong, sub, sup, var,
b, i,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, figcaption, figure,
footer, header, hgroup, menu, nav, section, summary,
time, mark, audio, video {
    margin:0;
    padding:0;
    border:0;
    outline:0;
    font-size:100%;
    vertical-align:baseline;
    background:transparent;
}

body {
    line-height:1;
}

article,aside,details,figcaption,figure,
footer,header,hgroup,menu,nav,section {
    display:block;
}

nav ul {
    list-style:none;
}

blockquote, q {
    quotes:none;
}

blockquote:before, blockquote:after,
q:before, q:after {
    content:'';
    content:none;
}

a {
    margin:0;
    padding:0;
    font-size:100%;
    vertical-align:baseline;
    background:transparent;
}

/* change colours to suit your needs */
ins {
    background-color:#ff9;
    color:#000;
    text-decoration:none;
}

/* change colours to suit your needs */
mark {
    background-color:#ff9;
    color:#000;
    font-style:italic;
    font-weight:bold;
}

del {
    text-decoration: line-through;
}

abbr[title], dfn[title] {
    border-bottom:1px dotted;
    cursor:help;
}

table {
    border-collapse:collapse;
    border-spacing:0;
}

/* change border colour to suit your needs */
hr {
    display:block;
    height:1px;
    border:0;  
    border-top:1px solid #cccccc;
    margin:1em 0;
    padding:0;
}

input, select {
    vertical-align:middle;
}

.home {
  display: flex;
  margin: 10px;
}

.button-side {
  margin-left: 10px;
}

.text-area  {
  margin: 30px 10px;
  display: flex;
}

.show-text {
    margin-left: 10px;
}

</style>
