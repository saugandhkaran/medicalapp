<template>
  <div class="home">
    <div class="question-container">
      <div class="top" @click="previousQuestion()" v-if="counter"></div>
      <div class="question-box">
        <h1 class="animate__animated animate__zoomIn" :key="counter">{{questions[counter].question}}</h1>
        <div class="options animate__animated animate__fadeIn" :key="counter">
          <button class="option" @click="nextAction(option, index)"
            v-for="(option, index) in questions[counter].options"
            :key="index">{{option.option}}</button>
        </div>
      </div>
    </div>
    <div class="image-container">
      <div class="image-box">
        <p v-if="currentImg">Related image</p>
        <ImageContainer :image="currentImg" :key="counter"/>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import ImageContainer from '@/components/ImageContainer.vue'

export default {
  name: 'Home',
  components: {
    ImageContainer
  },
  computed: {
    currentImg: function() {
      if (this.currentImage) {
        return this.currentImage
      }
    }
  },
  data() {
    return {
      counter: 0,
      currentImage: '',
      previousOption: 0,
      questions: [
        {
          question: "Which problem can I help you with?",
          options: [
            {
              option: "Eyes",
              image: "https://d2ebzu6go672f3.cloudfront.net/media/content/images/cr/7ae782c0-24f9-4128-97a9-8b64432bce76.jpg"
            },
            {
              option: "Heart",
              image: "https://www.heart.org/-/media/images/news/2019/february-2019/0225heartcancer_sc.png"
            },
            {
              option: "Brain",
              image: "https://img.webmd.com/dtmcms/live/webmd/consumer_assets/site_images/articles/image_article_collections/anatomy_pages/brain2.jpg?resize=646px:*&output-quality=100"
            }
          ]
        },
        {
          question: "what is the problem?",
          options: [
            {
              option: "Eye Sight",
              image: "https://www.maloneyvision.com/patient-education/online-books/life-without-glasses/why-you-need-glasses/images/why-you-need-glasses1.jpg"
            },
            {
              option: "Dryness",
              image: "https://www.mayoclinic.org/-/media/kcms/gbs/patient-consumer/images/2013/11/15/17/42/ds00463_-ds01096_im02751_r7_tearglandthu_jpg.jpg"
            },
            {
              option: "Tearing",
              image: "https://img.webmd.com/dtmcms/live/webmd/consumer_assets/site_images/articles/health_tools/why_are_my_eyes_watery_slideshow/493ss_getty_rf_watery_eye.jpg"
            }
          ]
        },
        {
          question: "Which side of eyes?",
          options: [
            {
              option: "Left",
              image: "https://d2ebzu6go672f3.cloudfront.net/media/content/images/bigstock-Human-eye-13953725.jpg"
            },
            {
              option: "Right",
              image: "https://images.fineartamerica.com/images-medium-large-5/1-right-eye-left-side-linda-magnanti.jpg"
            }
            
          ]
        },
        {
          question: "Which type of vision problem?",
          options: [
            {
              option: "Farsightedness",
              image: "https://cdn.britannica.com/44/63344-050-D20C0E4A/farsightedness-glasses-Hyperopia-lenses-effort-object-focus.jpg"
            },
            {
              option: "Nearsightedness",
              image: "https://cdn.britannica.com/45/63345-050-7BD73D28/nearsightedness-glasses-Myopia-lenses-focus-eye-objects.jpg"
            }
          ]
        }
      ],
      nextAction (option, optionIndex) {
        this.currentImage = option.image;
        this.previousOption = optionIndex;
        if(this.counter+1 ===  this.questions.length) {
          this.$router.push('/result');
        }
        this.counter++;
      },
      previousQuestion() {
        this.counter--;
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  p {
    text-align: center;
  }
  .home {
    display: grid;
    grid-template-columns: 8fr 4fr;
    min-height: 90vh;

    .top {
      width: 0;
      height: 0;
      border-left: 10px solid transparent;
      border-right: 10px solid transparent;
      border-bottom: 10px solid black;
      position: absolute;
      left: 50%;
      top: 10%;
      cursor: pointer;
    }

    .question-container {
      background-color: #FFF0D8;
      border-top-left-radius: 6px;
      border-bottom-left-radius: 6px;
      position: relative;

      .question-box {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
      }
    }
    .image-container {
      border-top-right-radius: 6px;
      border-bottom-right-radius: 6px;
      background-color: #F4C77E;
      position: relative;

      .image-box {
        position: absolute;
        min-width: 300px;
        min-height: 300px;
        border: 1px dotted grey;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
      }
    }
  }
  @media  screen and (max-width: 650px) {
  .home {
    grid-template-columns: 12fr;
  }
}
</style>
