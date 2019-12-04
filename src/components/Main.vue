<template>
  <div id="main">
    <div class="main-wrap">
      <RightSide></RightSide>
      <LeftSide></LeftSide>

      <div id="intro">
        <div class="intro-wrap">
          <div class="intro-text">
            <h1>正義和自由互為表裡，一旦分割，兩者都會失去。—富爾克</h1>
            <br>
            <p>這款桌遊是以真實事件發生過的事件改編，</p>
            <p>玩家會化身為人民或政府，</p>
            <p>兩者皆有屬於自己的目標，也藏有著改變歷史的關鍵，</p>
            <p>希望讓更多人可以藉此認識我們共同生活的這個家鄉，</p>
            <p>曾流過的血與看見那盼望著的—那顆心。</p>
          </div>
        </div>
      </div>

      <div id="story">
        <div class="title">
          <h1>遊戲故事</h1>
        </div>
        <div class="story-wrap">
          <div class="story-text" v-for="storyKey in story" :key="storyKey">
            <h2>{{ storyKey.title }}</h2>
            <p>{{ storyKey.content }}</p>
          </div>
        </div>
      </div>

      <div id="design">
        <div class="design-flex-wrap" v-show="imageDetailShow == false">
          <div class="title">
            <h1>美術設計</h1>
          </div>
          <div class="design-wrap">
            <div class="design-content">
              <div class="design-image-wrap">
                <div class="design-image-content" v-for="imageKey in image" :key="imageKey">
                  <img :class="'design-image'" :src="imageKey.link" @click="getImageData(imageKey.id), imageDetailShow = true"/>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="design-clicked-wrap" v-show="imageDetailShow == true" @click="imageDetailShow = false">
          <div class="title">
            <h1>美術設計</h1>
          </div>
          <div class="design-clicked-content">
            <div class="design-clicked-content-icon">
              <img src="../assets/image/design-i-1.png" v-if="image[imageDetailCount].icon_1 == true" />
              <img src="../assets/image/design-i-2.png" v-if="image[imageDetailCount].icon_2 == true" />
              <img src="../assets/image/design-i-3.png" v-if="image[imageDetailCount].icon_3 == true" />
              <img src="../assets/image/design-i-4.png" v-if="image[imageDetailCount].icon_4 == true" />
              <img src="../assets/image/design-i-5.png" v-if="image[imageDetailCount].icon_5 == true" />
            </div>
            <div class="design-clicked-content-image">
              <img :src="image[imageDetailCount].link"/>
            </div>
            <div class="design-clicked-content-name">
              <h2>{{ image[imageDetailCount].name }}</h2>
            </div>
            <div class="design-clicked-content-text">
              <p>{{ image[imageDetailCount].content }}</p>
            </div>
          </div>
        </div>
      </div>

      <div id="team">
        <div class="team-wrap">
          <div class="title">
            <h1>團隊成員</h1>
          </div>
          <div class="team-content-wrap">
            <div class="team-content" v-for="teamKey in team" :key="teamKey">
              <img :src="teamKey.image" />
              <h2>{{ '姓名：' + teamKey.name }}</h2>
              <h3>{{ '職務：' + teamKey.duty }}</h3>
            </div>
            <!-- <p class="aboutMe">簡單介紹</p> -->
          </div>
        </div>
      </div>

      <div id="contact">
        <div class="contact-wrap">
        <div class="title">
          <h1>聯絡我們</h1>
        </div>
          <div class="contact-content">
            <div class="contact-content-socialMedia">
              <a :href="contact.facebook" target="_blank"><font-awesome-icon :icon="['fab', 'facebook-square']"/></a>
              <a :href="contact.instagram" target="_blank"><font-awesome-icon :icon="['fab', 'instagram']"/></a>
            </div>
            <div class="contact-content-others">
              <h2 class="email">電子郵件 / E-mail： Ultimostudio.Taiwan@gmail.com</h2>
            </div>
          </div>
        </div>
      </div>

      <div id="toTop">
        <a href="#intro">
          <img src="../assets/image/to-top.png">
        </a>
      </div>

      <div class="copyright">
        <p>Copyright © 2019 UltimoStudio 末班工作室. All rights reserved</p>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
  #main {
    overflow-x: hidden;
    .main-wrap {
      // width: 100%;
      // height: 100%;

      #intro {
        width: 100vw;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        .intro-wrap {
          .intro-text {
            font-size: 25px;
            color: #ddd;
            text-shadow: 2px 2px #000000;
            h1 {
              font-size: 30px;
            }
          }
        }
      }
      #story {
        width: 100vw;
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 20px;
        .title {
          width: calc((100vw/10)*6);
          height: 100px;
          top: 100px;
          color: #ddd;
          text-shadow: 2px 2px 5px #000000;
          h1 {
            padding-bottom: 20px;
            border-bottom: #444 2px solid;
          }
        }
        .story-wrap {
          width: calc((100vw/10)*4);
          height: 80vh;
          padding: 20px;
          overflow-y: scroll;
          scrollbar-width: thin;
          scrollbar-color: dark;
          .story-text {
            line-height: 1.5;
            font-size: 20px;
            letter-spacing: 2.5px;
            color: #ddd;
            text-shadow: 1px 1px 3px #000000;
          }
        }
        .story-wrap::-webkit-scrollbar {
          width: 5px;
          height: 8px;
          background-color: #aaa;
        }
        .story-wrap::-webkit-scrollbar-thumb {
          background: #555;
        }
      }

      #design {
        width: 100vw;
        height: 100vh;
        position: relative;
        .title {
          width: calc((100vw/10)*6);
          height: 100px;
          top: 100px;
          color: #ddd;
          text-shadow: 2px 2px 5px #000000;
          h1 {
            padding-bottom: 20px;
            border-bottom: #444 2px solid;
          }
        }
        .design-flex-wrap {
          width: 100%;
          height: 100%;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          .design-wrap {
            .design-content {
              .design-image-wrap {
                width: calc((100vw/10)*6);
                height: 80vh;
                display: flex;
                flex-direction: row;
                justify-content: space-around;
                align-items: flex-start;
                flex-wrap: wrap;
                .design-image-content {
                  img {
                    height: 200px;
                    filter: grayscale(100) blur(3px);
                    border: #aaa 2px solid;
                  }
                  img:hover {
                    filter: grayscale(0) blur(0px);
                    border: #444 2px solid;
                  }
                }
              }
            }
          }
        }
        .design-clicked-wrap {
          z-index: 5;
          width: 100%;
          height: 100%;
          background: none;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          .title {
            width: calc((100vw/10)*6);
            height: 100px;
            top: 100px;
            color: #ddd;
            text-shadow: 2px 2px 5px #000000;
            h1 {
              padding-bottom: 20px;
              border-bottom: #444 2px solid;
            }
          }
          .design-clicked-content {
            width: calc((100vw/10)*6);
            height: 80vh;
            border-radius: 30px;
            background: rgba($color: #dddddd, $alpha: 0.1);
            .design-clicked-content-icon {
              display: inline;
              img {
                margin: 20px;
                width: 50px;
              }
            }
            .design-clicked-content-image {
              img {
                width: 40%;
              }
            }
            .design-clicked-content-name {
              h2 {
                font-size: 40px;
                color: #ddd;
                text-shadow: 2px 2px 5px #000000;
              }
            }
            .design-clicked-content-text {
              p {
                font-size: 30px;
                color: #ddd;
                text-shadow: 2px 2px 5px #000000;
              }
            }
          }
        }
      }

      #team {
        width: 100vw;
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        .team-wrap {
          width: 100%;
          height: 100%;
          background: none;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          .title {
            width: calc((100vw/10)*6);
            height: 100px;
            top: 100px;
            color: #ddd;
            text-shadow: 2px 2px 5px #000000;
            h1 {
              padding-bottom: 20px;
              border-bottom: #444 2px solid;
            }
          }
          .team-content-wrap {
            width: calc((100vw/10)*6);
            height: 80vh;
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: space-around;
            align-items: center;
            align-content: space-around;
            .team-content {
              width: 30%;
              height: 20vh;
              img {
                width: 10vw;
                border-radius: 50%;
                box-shadow: 2px 2px 5px #444;
              }
              h2 {
                color: #ddd;
                text-shadow: 2px 2px 5px #000000;
              }
              h3 {
                color: #ddd;
                text-shadow: 2px 2px 5px #000000;
              }
            }
          }
        }
      }

      #contact {
        width: 100vw;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        .contact-wrap {
          width: 100%;
          height: 100%;
          background: none;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          .title {
            width: calc((100vw/10)*6);
            height: 100px;
            top: 100px;
            color: #ddd;
            text-shadow: 2px 2px 5px #000000;
            h1 {
              padding-bottom: 20px;
              border-bottom: #444 2px solid;
            }
          }
          .contact-content {
            width: calc((100vw/10)*6);
            height: 80vh;
            .contact-content-socialMedia {
              height: 40%;
              font-size: 150px;
              margin-top: 100px;
              border-bottom: #aaa 2px solid;
              a {
                text-decoration: none;
                color: #444;
                padding: 50px;
              }
            }
            .contact-content-others {
              .email {
                color: #ddd;
                text-shadow: 2px 2px 5px #000000;
              }
            }
          }
        }
      }

      #toTop {
        position: fixed;
        right: 280px;
        bottom: 50px;
        a {
          img {
            width: 40px;
          }
        }
      }
    }
  }
</style>

<script>
import LeftSide from '@/components/LeftSide'
import RightSide from '@/components/RightSide'

export default {
  components: {
    LeftSide,
    RightSide
  },
  data () {
    return {
      imageDetailShow: false,
      imageDetailCount: 0,
      team: [
        {
          name: '邱旻鋒',
          duty: '前端設計、工程',
          image: 'https://i.imgur.com/oaWZdfz.jpg'
        },
        {
          name: '唐苡晴',
          duty: '專案經理、行銷',
          image: 'https://i.imgur.com/MarKtUu.jpg'
        },
        {
          name: '莊浣茜',
          duty: '文書內容、故事',
          image: 'https://i.imgur.com/WRq9yqv.jpg'
        },
        {
          name: '洪霆揚',
          duty: '場務設計、行政',
          image: 'https://i.imgur.com/jvkeSda.jpg'
        },
        {
          name: '陳亞松',
          duty: '美術設計、繪圖',
          image: 'https://i.imgur.com/GqtGuKo.jpg'
        }
      ],
      story: {
        partOne: {
          title: '第一章 前言',
          content: `
            結束日本殖民時期的台灣，此時台灣人的認知及價值觀，已與戰後中國移民有明顯的差距。相對地，戰後中國移民及政府官員對台灣的情形，亦非常陌生，加上當時中國內陸戡亂情勢日趨惡化，政府自然沒有心力對台灣付出更多的關懷，而主政者不能體察民情，還在政治上打壓台籍人士。
            天這麼黑，為什麼爸爸還不回家……
            躺在床上翻來覆去，眼睛直愣愣地盯著天花板，臉上全是擔憂，今夜又是個失眠夜，害怕又夢到地上佈滿鮮血，無辜的人民在路上逃竄。
            更害怕夢境中爸爸在街上消逝的身影變真實。
            第二次世界大戰剛結束，滿地的鮮血與屍體還深深印烙在人們的心裡，大家都害怕再有戰爭發生，「生靈塗炭」是我腦海中唯一想到的詞。或許在這個世代，不信任人心才是對的，一點風聲草動，都有著足以威脅自己生命的事情發生，寧願錯殺一百也不願放過一個……
            `
        },
        partTwo: {
          title: '第二章  導火線',
          content: `
            我的爸爸是當時小有名氣的律師，那天有位醫師協會的人跑來找爸爸，臉上寫滿了憂愁，苦苦的哀求爸爸為他打官司。
            原來這家醫院為一位軍官的妻子開刀，但不幸的是，妻子因為藥物反應不良而撒手人寰，軍官怒氣沖天，無法原諒這家醫院，也不能相信妻子就此逝去的事實，因此憤而對這家醫院提告。
            爸爸的直率、正直是眾所皆知的，因此當其他律師都害怕得罪國家的同時，爸爸接下了這樁案子，為了追求正義。藥物的反應不良是不可抗力的死亡原因，爸爸在法官面前堅持著這個因素，為醫師協會打了場勝仗，但卻為自己埋下逃亡的伏筆……
            `
        },
        partThree: {
          title: '第三章  經過',
          content: `
            1947年黑暗的序幕被掀開，一樁樁台灣人被莫須有的罪名而送入大牢，甚至死亡的冤案發生了，爸爸雖心有不滿，但為了家人的安全並沒有太張揚，只是安靜地過日子。
            有一天，爸爸的友人—楊叔叔來家裡找他，相談甚歡，吃著食物喝著酒，日子看起來平凡而快樂。正當話題十分盡興時，猝不及防地，門被硬生生踢開，為軍官夫人執刀的那名醫生急忙地跑進來，拉著爸爸就要跑，大家都被他搞的一頭霧水。

            醫生：「快走！不然就來不及了。」
            爸爸：「到底怎麼回事，你一進門就拽著我走。」
            醫生：「我也不想啊，但李律師您救過我，我不能這樣見死不救，更何況這件事算是因我而起。」
            爸爸一臉震驚，大概猜想到是怎麼回事了，但誰也沒想到平凡的日子裡，會有人衝進家門口對自己說有生命危險。
            爸爸：「你說清楚一點。」
            醫生：「來不及了，我們先走，路上再跟你說。」
            爸爸被醫生拉走，離開了這個家。

            在爸爸離開後的幾分鐘，果不其然，一位軍官大搖大擺地進入家中，看了看我們的房子，一出口便要大批軍人搜我們家。
            媽媽：「這是怎麼回事，這位軍官，你突然到我們家來搜查，有法律依據嗎？」
            軍官藐視地看著母親：「法律？李瑞和打錯官司，掩蔽罪人，讓那家破醫院判定無罪，是重要犯人，我要將他緝拿到案。」
            一名軍人來報，搜盡家中沒有找到爸爸。這是理所當然的，因為爸爸早就跑了。
            楊叔叔：「你這根本是莫須有的罪名，有沒有罪不是你決定的。」
            軍官：「你是誰？也敢這樣跟我講話！」
            媽媽趕緊攬住楊叔叔，希望他不要為了替爸爸出氣而得罪軍官。

            媽媽：「不管有沒有罪，我丈夫現在外出了，有什麼事我們法庭上再談。」
            軍官：「是不是外出等我抓到他就知道了。 來人，把這個出口不遜的人綁回去。而妳，告訴李瑞和最好不要搞什麼花招，乖乖認罪。」
            軍官帶走楊叔叔與大批人馬，留下擔心受怕的母親與混亂不堪的房子……
            那時我在學校上學，這些事是回家後母親流著淚告訴我的，我很難再見到爸爸了。
          `
        },
        partFour: {
          title: '第四章  逃亡',
          content: `
            「要去哪裡？」我的腦袋裡一片空白，只有剛剛發生的事還回盪在腦海中，我急切地抓住這位年輕的醫生，只想趕快弄清楚發生什麼事。
            「真的很抱歉…但我也是逼不得已的」醫生滿懷愧疚地說出，軍官曾跑來醫院嗆聲，以及醫院的長官是如何把事情推給他的。律師救了自己，但自己卻害他陷入危險，因此一聽到軍官往律師家方向去之後，這位年輕的醫師便決定放下自己大好的前程，無論如何也要救這位救命恩人。
          
            大量的資訊困擾著思緒，震驚顯露在臉上，緊接著的是竄上全身的害怕。
            「我的家人！」轉身就想要跑回家裡，保護自己的妻子，但迅即被醫師抓住，「冷靜點，他們的目標是你，不是你的家人，你現在跑回去是自投羅網」。
            我扶著額頭、腳步踉蹌，彷彿要被這個天大的消息壓垮，醫生急切地扶住我，安慰地說「我們必須先逃跑，活下去，才有希望」
            明白事情已經無轉圜餘地，在這個時代，我註定是逃犯。一開始我們只想要逃，接應我們的家人，離開台灣，但政府的力量滲透全台各地，讓我們去哪都不方便。
          `
        },
        partFive: {
          title: ' 第五章  起義',
          content: `
            一旦明白這件事後，我心想，那只剩一個選擇了，我們決定起義，為自由努力一次。
            228事件爆發後，冤案不斷發生，因此對政府不滿的人比比皆是，我不斷拉攏那些人，讓自己的組織越來越龐大，組織名稱是「末班」，忠誠於組織的人們，有一個絕對不能交出去的東西，那就是名單，上面記載了所有參加末班的人員名字，一旦曝光，所有的人都將死在國家手上，無一倖免。
          `
        }
      },
      image: [
        {
          id: 1,
          name: '口琴',
          link: 'https://i.imgur.com/95pzLF5.png',
          content: '爸爸和媽媽的定情物',
          icon_1: false,
          icon_2: true,
          icon_3: true,
          icon_4: false,
          icon_5: false
        },
        {
          id: 2,
          name: '鋼筆',
          link: 'https://i.imgur.com/ufEyK0j.png',
          content: '工作時使用的鋼筆',
          icon_1: false,
          icon_2: true,
          icon_3: false,
          icon_4: false,
          icon_5: false
        },
        {
          id: 3,
          name: '台幣',
          link: 'https://i.imgur.com/WlWV48y.png',
          content: '台灣銀行所發行的貨幣',
          icon_1: true,
          icon_2: true,
          icon_3: true,
          icon_4: true,
          icon_5: false
        },
        {
          id: 4,
          name: '手帕',
          link: 'https://i.imgur.com/hv7wGRd.png',
          content: '這是媽媽親手編織的手帕',
          icon_1: false,
          icon_2: false,
          icon_3: true,
          icon_4: false,
          icon_5: false
        },
        {
          id: 5,
          name: '地瓜粥',
          link: 'https://i.imgur.com/2K3EpWx.png',
          content: '最近物價上漲，便宜能果腹的地瓜，是最好的選擇',
          icon_1: true,
          icon_2: true,
          icon_3: true,
          icon_4: true,
          icon_5: false
        },
        {
          id: 6,
          name: '醫療箱',
          link: 'https://i.imgur.com/PzbtyW0.png',
          content: '裝滿醫療器材的箱子',
          icon_1: true,
          icon_2: false,
          icon_3: false,
          icon_4: false,
          icon_5: false
        },
        {
          id: 7,
          name: '菸',
          link: 'https://i.imgur.com/WJWF1EN.png',
          content: '讓人短暫逃離世俗的煩惱',
          icon_1: true,
          icon_2: true,
          icon_3: false,
          icon_4: false,
          icon_5: false
        },
        {
          id: 8,
          name: '照片',
          link: 'https://i.imgur.com/v2WrY5A.png',
          content: '我們的全家福照片',
          icon_1: false,
          icon_2: false,
          icon_3: true,
          icon_4: true,
          icon_5: false
        },
        {
          id: 9,
          name: '課本',
          link: 'https://i.imgur.com/tbVCFbM.png',
          content: '學習知識能夠使我快樂',
          icon_1: false,
          icon_2: false,
          icon_3: false,
          icon_4: true,
          icon_5: false
        },
        {
          id: 10,
          name: '糖果',
          link: 'https://i.imgur.com/qxMkIEZ.png',
          content: '平時最喜歡吃的零食',
          icon_1: true,
          icon_2: false,
          icon_3: false,
          icon_4: true,
          icon_5: false
        },
        {
          id: 11,
          name: '口糧',
          link: 'https://i.imgur.com/MG2ZVaa.png',
          content: '暫時止飢的緊急糧食',
          icon_1: false,
          icon_2: false,
          icon_3: false,
          icon_4: false,
          icon_5: true
        },
        {
          id: 12,
          name: '槍',
          link: 'https://i.imgur.com/0vBv3LQ.png',
          content: '叛徒必須接受制裁',
          icon_1: false,
          icon_2: false,
          icon_3: false,
          icon_4: false,
          icon_5: true
        },
        {
          id: 13,
          name: '軍用醫療箱',
          link: 'https://i.imgur.com/INZbIif.png',
          content: '裝滿醫療器材的箱子',
          icon_1: false,
          icon_2: false,
          icon_3: false,
          icon_4: false,
          icon_5: true
        },
        {
          id: 14,
          name: '睡袋',
          link: 'https://i.imgur.com/VXIepWD.png',
          content: '睡袋的保暖效果，能幫助我們度過寒冬',
          icon_1: false,
          icon_2: false,
          icon_3: false,
          icon_4: false,
          icon_5: true
        },
        {
          id: 15,
          name: '彈夾',
          link: 'https://i.imgur.com/J7LP5Kg.png',
          content: '隨時填充子彈上膛',
          icon_1: false,
          icon_2: false,
          icon_3: false,
          icon_4: false,
          icon_5: true
        }
        // {
        //   name: '水壺',
        //   link: 'https://i.imgur.com/KsJDmfI.png',
        //   content: '水是不可或缺的資源',
        //   icon_1: false,
        //   icon_2: false,
        //   icon_3: false,
        //   icon_4: false,
        //   icon_5: true
        // }
      ],
      contact: {
        facebook: 'https://www.facebook.com/UltimoGames',
        instagram: 'https://www.instagram.com/ultimostudio.tw/'
      }
    }
  },
  methods: {
    getImageData (value) {
      this.imageDetailCount = 0
      this.imageDetailCount = value - 1
    }
  }
}
</script>
