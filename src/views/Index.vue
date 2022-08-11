<!--
  * 앱제작 팀프로젝트(4조_박소윤, 이주현, 김시온, 송은경) : 마음아지트

    * 메인 페이지(index)
    * 작성자 : 이주현
    * 작성일 : 2022.07.20
    * 업데이트 : 2022.07.27 (수정 : 이주현, 박소윤, 송은경)
    
    //// : 시멘틱 영역표시
    ???? : 해결해야할 부분
    !!!! : 수정사항
 -->

<template>
    <!-- <transition name="fadeOut">
        <Splesh v-if="intro == true"></Splesh>
    </transition> -->
    <div class="wrap">
        <h1 class="hidden">마음아지트 메인</h1>
        <!-- //// 헤더 //// -->
        <header>
            <!-- 글로벌 네비 -->
            <div class="global_nav">
                <div class="GNV_relative">
                    <div class="btns">
                        <a href="#none" class="plus_bt"><img src="../assets/indexView/main_plus_bt.png" alt="글로벌네비게이션 더보기"></a>
                        <div class="plus_touch_show">
                            <a href="#none" class="refresh_bt"><img src="../assets/indexView/main_refresh_bt.png" alt="새로고침"></a>
                            <a href="#none" class="share_bt"><img src="../assets/indexView/main_share_bt.png" alt="공유하기"></a>
                            <a href="#none" class="setting_bt"><img src="../assets/indexView/main_setting_bt.png" alt="설정"></a>
                        </div>
                    </div>
                </div>
            </div>
            <!-- 프로필 영역 -->
            <div id="profile_field">
                <div class="profile_info">
                    <p class="login_date">
                        <span>1</span>일째
                    </p>
                    <p class="hello">안녕하세요 <br>
                        <span>만성피로맨</span>님</p>
                    <p class="phrase_title">One sentence for today</p>
                    <p class="phrase">나만이 내 인생을 바꿀 수 있다<br> 아무도 날 대신해 줄 수 없다</p>
                </div>
                <!-- !!!!(07.29) : 링크용 -->
                <a href="splash.html">
                    <div class="profile_img">
                        <img src="../assets/indexView/main_profile_img.png">
                    </div>
                </a>
                <!-- <div class="profile_img">
                    <img src="../assets/indexView/main_profile_img.png">
                </div> -->
            </div>
        </header>

        <!-- //// 섹션 //// -->
        <section>
            <!-- 힐링상품 배너 -->
            <div class="healing_banner">
                <!-- <h2>Healing product</h2> -->
                <div class="slide_container">

                    <div class="slide_img" v-for="(a,i) in healingBanner" :key="i">
                        <img :src="healingBanner[i].img" alt="힐링상품 배너" draggable="false">
                        <p>{{ healingBanner[i].content }}</p>
                    </div>
                </div>
            </div>

            <!-- 인기 미디어 목록 -->
            <div class="popular">
                <h2>Popular meditation</h2>
                <div class="slide_container">
                    <div class="silde_box" v-for="(a,i) in popular" :key="i" :style="{ backgroundImage : `url(${popular[i].img})`, backgroundSize : 'cover' }">
                        <div class="contents_field">
                            <p>{{ popular[i].content }}</p>
                            <img src="../assets/indexView/main_contentsPlay_icon.png" alt="인기미디어-플레이">
                        </div>
                    </div>
                </div>
            </div>

            <!-- 새로운 미디어 목록 -->
            <div class="new">
                <h2>New meditation</h2>
                <div class="slide_container">
                    <div class="silde_box" v-for="(a,i) in newMedia" :key="i" :style="{ backgroundImage : `url(${newMedia[i].img})`, backgroundSize : 'cover' }">
                        <div class="contents_field">
                            <p>{{ newMedia[i].content }}</p>
                            <img src="../assets/indexView/main_contentsPlay_icon.png" alt="새미디어-플레이">
                        </div>
                    </div>
                </div>
            </div>

            <!-- 힐링클래스 배너 -->
            <div class="class_banner">
                <h2 class="class">Class</h2>
                <div class="class_banner_slide">
                    <div class="slide_container">
                        <div class="slide_img" v-for="(a,i) in classBanner" :key="i">
                            <div class="text_field">
                                <p class="title">OFFLINE CLASS 1<span>기 모집중</span></p>
                                <p class="content">{{ classBanner[i].content }}</p>
                                </div>
                                <img :src="classBanner[i].img" alt="힐링클래스-배너" draggable="false">
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <!-- //// 푸터 //// -->
        <Footer></Footer>
    </div>
</template>

<script>
import Footer from '../components/Footer.vue';
// import Splesh from './Splesh.vue';

export default {
    data() {
        return {
            intro : true,
            healingBanner : [
                {
                    img : require('../assets/indexView/main_healingBannerImg_00.jpg'),
                    content : '일상 속 휴식선물 01',
                },
                {
                    img : require('../assets/indexView/main_healingBannerImg_01.jpg'),
                    content : '일상 속 휴식선물 02',
                },
                {
                    img : require('../assets/indexView/main_healingBannerImg_02.jpg'),
                    content : '일상 속 휴식선물 03',
                }],
            popular : [
                {
                    content : `우주와 함께하는
                    시간00`,
                    img : require('../assets/indexView/main_popular_00.jpg'),
                },
                                {
                    content : `우주와 함께하는
                    시간01`,
                    img : require('../assets/indexView/main_popular_01.jpg'),
                },
                                {
                    content : `우주와 함께하는
                    시간02`,
                    img : require('../assets/indexView/main_popular_02.jpg'),
                }],
                newMedia : [
                {
                    content : `마음 속 평안을
                    찾는 여행00`,
                    img : require('../assets/indexView/main_new_00.jpg'),
                },
                {
                    content : `마음 속 평안을
                    찾는 여행01`,
                    img : require('../assets/indexView/main_new_01.jpg'),
                },
                {
                    content : `마음 속 평안을
                    찾는 여행02`,
                    img : require('../assets/indexView/main_new_02.jpg'),
                }],
                classBanner : [
                {
                    img : require('../assets/indexView/main_classBannerImg_00.jpg'),
                },
                {
                    img : require('../assets/indexView/main_classBannerImg_01.jpg'),
                },
                {
                    img : require('../assets/indexView/main_classBannerImg_02.jpg'),
                }],
        }
    },
    components: {
        Footer : Footer,
        // Splesh : Splesh,
    },
    mounted() {

        // 2초 후에 <Discount> 사라지게?
        setTimeout (()=> { // arrow function 쓰는 이유 : this를 바깥에있는 this를 제대로 잘 가져다 쓰기 위해서 (그래서 여기서는 arrow function으로 써야함)

            // 실행할 코드
            // 할인홍보배너 닫아주셈
            this.intro = false;
        }, 1000);
    },
    methods: {
        
    }
}
</script>

<style scoped>


@charset "utf-8";

* {
    margin: 0;
    padding: 0;
    border: 0;
    outline: 0;
    box-sizing: border-box;
    font-family: "Noto Sans", Avenir, Helvetica, Arial, sans-serif;
    /* !!!!(07.28) : 추가 나머지 다 제거 */
    color: #333;
}

a {
    text-decoration: none;
    color: #333;
}

ul,li {
    list-style: none;
}

.cf::after {
    content: '';
    display: block;
    clear: both;
}

.hidden {
    display: none;
}

/* 모바일 수평 스크롤 금지 */
html,
body {
    max-width: 100%;
    overflow-x: hidden;

    /* y축 스크롤바 숨기기(작동o) */
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

/* y축 스크롤바 숨기기(작동o) */
.html,
body::-webkit-scrollbar {
    display: none;
    /* Chrome, Safari, Opera*/
}

/* //// 레이아웃 시작 //// */

/* 스플래쉬 애니메이션 */
/* modal_transition_01_CSS */
.aniStart {opacity: 0;  transition: all 1s;}
.aniEnd {opacity: 1;}

/* modal_transition_02_모달창 퇴장 애니메이션 : 작명-enter-from/active/to */
.fadeOut-leave-from {opacity: 1;} /* 시작 */
.fadeOut-leave-active {transition: all 1s;}
.fadeOut-leave-to {opacity: 0;} /* 끝 */


h2 {
    font-size: 25px;
    font-weight: 600;
    margin-bottom: 25px;
    text-align: center;
}

.wrap {
    width: 100%;
    max-width: 767px;
    min-width: 425px;
    margin: 0 auto;
    /* border: 1px solid #000; */
}

/* //// 헤더 //// */
header {
    width: 100%;
    margin: 0 auto;
    height: 317px;
    padding-top: 1px;
    border-radius: 0 0 0 35px;
    background-color: #ecf4eb;
    position: relative;
    overflow: hidden;
}

/* 글로벌 네비 */
.global_nav {
    /* display: none; */
    width: 160px;
    height: 50px;
    background-color: #68b39f;
    border-radius: 26px 0 0 26px;
    position: absolute;
    top: 40px;
    right: -80px;
    /* 터치전/후 80px 차이 */
}

.GNV_relative {
    position: relative;
    width: 100%;
    height: 100%;
}

.btns {
    width: 160px;
    height: 50px;
    margin-top: 2px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.plus_bt {
    display: block;
    width: 40px;
    height: 40px;
    margin-top: 2px;
    position: absolute;
    /* !!!!(07.28) : 버튼 이동 */
    left: 6px;
    /* display: none; */
}

.plus_touch_show {
    width: 85%;
    height: 40px;
    display: flex;
    /* !!!!(07.28) : 버튼 이동 */
    margin-top: 2px;
    /* !!!!(07.28) : 버튼 이동 */
    margin-right: 12px;
    justify-content: space-between;
    display: none;
}

.plus_touch_show a {
    display: block;
    width: 40px;
    height: 40px;
}

/* 프로필 영역 */
#profile_field {
    width: 85%;
    height: 70%;
    margin: 40px auto;
    /* background-color: white; */
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.profile_info {
    /* !!!!(07.28) : 너비조정 */
    width: 65%;
    height: 100%;
    /* background-color: lightblue; */
}

/* 접속일 */
.login_date span {
    font-size: 35px;
    font-weight: 600;
    color: #68b39f;
    display: inline-block;
    margin-bottom: 20px;
}

/* 일째 */
.login_date {
    /* !!!!(07.28) : 폰트사이즈, 색상 없앰(초기화에 추가) */
    font-size: 20px;
}

/* 안녕하세요 */
.hello {
    font-size: 20px;
    font-weight: 400;
    margin-bottom: 20px;
}

/* 닉네임 */
.hello span {
    font-size: 28px;
    font-weight: 600;
}

/* 오늘의 명언 타이틀 */
p.phrase_title {
    font-size: 18px;
    font-weight: 600;
    color: #2d6974;
    margin-bottom: 10px;
}

/* 명언 */
.phrase {
    font-size: 18px;
    /* !!!!(07.28) : 자간 */
    letter-spacing: -1px;
    line-height: 1.5em;
}

/* 프로필 이미지 */
.profile_img {
    /* !!!!(07.28) : 사진크기 조정 */
    width: 100px;
    height: 100px;
    /* margin-top: 30px; */
    
    /* background-color: #68B39F; */
}

.profile_img img {
    width: 100%;
}

/* //// 섹션 //// */
section {
/*     display: flex;
    flex-flow: column nowrap;
    justify-content: center; */
    width: 100%;
    height: auto;
    /* !!!!(07.28) : 하단여백 수정 */
    /* 개별 */
    margin: 0 auto 66px;
}

/* 힐링배너 */
.healing_banner {
    width: 100%;
    overflow: hidden;
    margin: 50px auto;
}

.healing_banner .slide_container {
    width: 300%;
    display: flex;
    transition: all .5px;
    /* transform: translateX(-100vw); */
}

.healing_banner .slide_img {
    width: 100%;
    position: relative;
}

.healing_banner .slide_img img {
    width: 100%;
}

.healing_banner p {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    /* !!!!(07.28) : 글꼴스타일 추가 */
    font-size: 22px;
    color: #333;
    letter-spacing: -1px;
}

/* !!!!(07.28) : 글꼴스타일 추가 */
.healing_banner p span {
    font-size: 24px;
    font-weight: 800;
}

/* 인기 미디어 목록 */
.popular {
    width: calc(100% - 40px);
    height: auto;
    margin: 50px auto;
    /* border: 1px solid #333; */
}

.popular .slide_container {
    width: 300%;
    display: flex;
    transition: all .5s;
}

.popular .silde_box {
    width: 150px;
    height: 150px;
    margin-right: 2%;
    border-radius: 25px;
    position: relative;
}

/* !!!!(07.28) : 추가 */
.popular p {
    letter-spacing: -1px;
}

.popular .contents_field {
    position: relative;
    top: 10%;
    left: 50%;
    transform: translateX(-50%);
    width: 80%;
    height: 80%;
}

.popular .contents_field p {
    color: #ffffff;
}

.popular .contents_field img {
    position: absolute;
    width: 30px;
    height: 30px;
    right: 0;
    bottom: 0;
}

/* 새로운 미디어 목록 */
.new {
    width: calc(100% - 40px);
    height: auto;
    margin: 50px auto;
    /* border: 1px solid #333; */
}

.new .slide_container {
    width: 300%;
    display: flex;
    transition: all .5s;
}

.new .silde_box {
    width: 150px;
    height: 150px;
    margin-right: 2%;
    border-radius: 25px;
    position: relative;
}

/* !!!!(07.28) : 추가 */
.new p {
    letter-spacing: -1px;
}

.new .contents_field {
    position: relative;
    top: 10%;
    left: 50%;
    transform: translateX(-50%);
    width: 80%;
    height: 80%;
}

.new .contents_field p {
    color: #ffffff;
}

.new .contents_field img {
    position: absolute;
    width: 30px;
    height: 30px;
    right: 0;
    bottom: 0;
}

/* 힐링클래스 배너 */
.class_banner {
    width: 100%;
    margin: 0 auto 50px;
    padding: 50px 0px;
    background-color: #ecf4eb;
}

.class_banner_slide {
    width: 100%;
    height: auto;
    /* background-color: yellowgreen; */
    overflow: hidden;
}

.class_banner .slide_container {
    width: 300%;
    display: flex;
    transition: all .5s;
}

.class_banner .slide_img {
    width: 100%;
    /* background-color: #68b39f; */
    position: relative;
}

.class_banner img {
    width: 90%;
    height: 100%;
    /* !!!!(07.28) : 수정 */
    border-radius: 25px;
    overflow: hidden;
    display: block;
    margin: 0 auto;
}

/* !!!!(07.28) : 추가 */
.class_banner .text_field {

    width: 80%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    letter-spacing: -1px;
    line-height: 40px;
    /* background-color: rgba(255, 255, 255, .5); */
}

/* 배너타이틀 */
.class_banner .title {
    font-size: 23px;
    font-weight: 600;
}

/* 배너타이틀 한글부분 */
.class_banner .title span {
    font-weight: 800;
}

.class_banner .content {
    font-size: 18px;
}


</style>