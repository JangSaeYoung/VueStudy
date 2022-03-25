<template>

<div class= "black-bg" v-if="모달창열렸니 == true">   
  <!-- v-if="조건식" -->
  <!-- 조건식이 참일 때(1==1처럼)만 HTML보여줌 -->
  <div class= "white-bg" v-if="모달창닫기 == false">
    <h4>상세페이지</h4>
    <p>상세페이지 내용</p>
    <button @click="모달창닫기 = true">닫기</button>
  </div>
</div>


<div class="menu">
  <a v-for="a in 메뉴들" :key="a">{{a}}</a>   
</div>


<div>
  <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="모달창열렸니 = true">{{products[0]}}</h4>
    <p>70만원</p>
    <button @click="신고수[0]++">허위매물신고</button> 
    <span>신고수 : {{신고수[0]}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg">
    <h4>{{products[1]}}</h4>
    <p>70만원</p>
    <button @click="신고수[1]++">허위매물신고</button>
    <span>신고수 : {{신고수[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg">
    <h4>{{products[2]}}</h4>
    <p>90만원</p>
    <button @click="신고수[2]++">허위매물신고</button>
    <span>신고수 : {{신고수[2]}}</span>
  </div>
</template>

<script>

export default { 
  name: 'App',
  data(){   // React에서는 state(상태)라고도 부른다. 
    return{ 
      모달창열렸니 : false,    //1-1모달창의 상태를 내가 정해서 작성 ex) 1 은 열렸다. 아니면 true 는 열렸다 이렇게.
      모달창닫기 : false,
      신고수: [0,0,0],
      메뉴들 : ['Home', 'Shop', 'About'],   
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods: {
      increase(){
        this.신고수[0] +=1; 
      }
  },

  components: {
  }
}
</script>

<style>
body {
  box-sizing: 0;
}

div {
  box-sizing: border-box;
}

div h4 {
  cursor: pointer;
}

.black-bg {
  width: 100%;
  height: 100%;
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background-color: white;
  border-radius: 8px;
  padding: 20px;
}
 
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
} 

.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
