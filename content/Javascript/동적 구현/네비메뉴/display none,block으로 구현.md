---
title: "2단 네비바"
date: 2023-02-21 9:51:13
subtitle: "2단 네비바 만들기 (계속 여러방법 업뎃하기)"
category: "Blog"
draft: false
---

## 1. display none, block 활용해서 만들기

<hr/>

### html구조

상단 메뉴

```javascript
<nav id="nav">
      <div class="nav_bar">
        <div class="logo_box">
          <a href="#"><img src="./img/logo.png" alt=""></a>
          <div class="event_logo"><a href="#"><img src="./img/50th_logo.gif" alt=""></a></div>
        </div>
        <!-- nav sec1 -->

        <div class="one_depth">
          <ul class="one_depth_menu_list">
            <li><a href="#">시정소식</a></li>
            <li><a href="#">전자민원</a></li>
            <li><a href="#">시민참여</a></li>
            <li><a href="#">정보공개</a></li>
            <li><a href="#">성남소개</a></li>
            <li><a href="#">분야별정보</a></li>
          </ul>
        </div>
        <!-- nav sec2 -->

        <div class="ico_list">
          <a href=""><span class="hamberger_ico"></span></a>
          <a href=""><span class="searching_ico"></span></a>
        </div>
        <!-- nav sec3 -->

      </div>
    </nav>
    <!-- nav -->
```

2뎁스 메뉴

```javascript
<div class="hidden_nav_depth">
      <div class="nav_depth">
        <div class="nav_depth_container">
          <ul class="nav_depth_container_box">
            <li><a href="#">새소식</a></li>
            <li><a href="#">행사/강좌/공모</a></li>
            <li><a href="#">고시공고</a>
              <ul>
                <li><a href="#">전체</a></li>
                <li><a href="#">고시</a></li>
                <li><a href="#">입찰공고</a></li>
                <li><a href="#">입법예고</a></li>
                <li><a href="#">일반공고</a></li>
                <li><a href="#">개인정보제3자제공</a></li>
                <li><a href="#">개인정보처리위탁</a></li>
              </ul>
            </li>
            <li><a href="#">채용정보</a>
              <ul>
                <li><a href="#">채용공고</a></li>
                <li><a href="#">채용/시험</a></li>
              </ul>
            </li>
            <li><a href="#">성남시의회입법예고</a></li>
            <li><a href="#">보도자료</a></li>
            <li><a href="#">브리핑(주요시정알림)</a></li>
            <li><a href="#">언론보도해명</a></li>
            <li><a href="#">성남시보</a></li>
            <li><a href="#">무연분묘개장공고</a></li>
            <li><a href="#">도정소식</a>
              <ul>
                <li><a href="#">보도게시판</a></li>
                <li><a href="#">기사게시판</a></li>
                <li><a href="#">경기도민생범죄통계</a>
              </ul>

            </li>
            <li><a href="#">시정소식지비전성남</a></li>
          </ul>
        </div>
      </div>
    </div>
```

### css 구조

```javascript
.one_depth_menu_list{
        display: flex;
        li{
          padding: 42px 0px;
          &:hover a{
            color: #d84048;
            transition: all 0.3s;
          }
          height:100%;
          a{
            align-items: center;
            justify-content: center;
            height: 100%;
            padding: 0 29px;
            font-weight: 900;
            font-size: 21px;
          }
        }

      }
```

```javascript
.hidden_nav_depth{
    .nav_depth{
      display: none;
      width: 100%;
      position : absolute;
      top:144px;
      height:500px;
      z-index: 1;
      border-top: 2px solid #ececec;
      border-bottom: 2px solid #ececec;
      .nav_depth_container{
        max-width: 1400px;
        margin: 30px auto;
        .nav_depth_container_box{
          display: flex;
          flex-wrap: wrap;
          li{
            width:19%;
            ul{
              margin:11px 0px 15px 0px;
              li{
                width:100%;
                a{
                  font-size: 14px;
                  font-weight: lighter;
                  border:none;
                }
                a::before{
                  width:10px;
                  height:10px;
                  border:1px solid black;
                }
              }
            }
            a{
              display: block;
              font-size: 16px;
              font-weight: bolder;
              position: relative;
              width: 100%;
              padding: 7px 15px;
              color: #555;
              transition: .3s;
              background-color: #fff;
              border: 1px solid #c5c9d6;
              border-radius: 5px;
              box-sizing: border-box;
            }
          }
        }
      }
    }
    .nav_depth:nth-child(1){
      background-color: white;
      li{
        margin-right: 10px;
      }
    }
    .nav_depth:nth-child(2){
      background-color: white;
      height:430px;
      li{
        margin-right: 10px;
      }
    }
    .nav_depth:nth-child(3){
      background-color: rgb(59, 59, 114);
    }
    .nav_depth:nth-child(4){
      background-color: rgb(53, 131, 45);
    }
    .nav_depth:nth-child(5){
      background-color: rgb(148, 174, 46);
    }
    .nav_depth:nth-child(6){
      background-color: rgb(174, 46, 142);
    }
  }
```

### 자바스크립트

```javascript
const navHover = document.querySelectorAll(".one_depth_menu_list>li");
const navDepth1 = document.querySelectorAll(".hidden_nav_depth>.nav_depth");

for (let i = 0; i <= navHover.length; i++) {
  navHover[i].addEventListener("mouseover", () => {
    navDepth1[i].style.display = "block";
  });
  navDepth1[i].addEventListener("mouseover", () => {
    navDepth1[i].style.display = "block";
  });
  navHover[i].addEventListener("mouseout", () => {
    navDepth1[i].style.display = "none";
  });
  navDepth1[i].addEventListener("mouseout", () => {
    navDepth1[i].style.display = "none";
  });
}
```
