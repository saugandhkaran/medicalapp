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
          question: "How are you doing?",
          options: [
            {
              option: "Well",
              image: "https://source.unsplash.com/W5OwUWIvMa8/300x300"
            },
            {
              option: "Not good",
              image: "https://source.unsplash.com/8rj4sz9YLCI/300x300"
            },
            {
              option: "Great",
              image: "https://source.unsplash.com/R6NucBqVIaM/300x300"
            }
          ]
        },
        {
          question: "What is your thing",
          options: [
            {
              option: "Lorem",
              image: "https://source.unsplash.com/701-FJcjLAQ/300x300"
            },
            {
              option: "Ipsum",
              image: "https://source.unsplash.com/7JX0-bfiuxQ/300x300"
            },
            {
              option: "Wow",
              image: "https://source.unsplash.com/Us3AQvyOP-o/300x300"
            }
          ]
        },
        {
          question: "Blah blah blah?",
          options: [
            {
              option: "Yes",
              image: "https://source.unsplash.com/w9KEokhajKw/300x300"
            },
            {
              option: "No",
              image: "https://source.unsplash.com/CKxD_Qh6ULY/300x300"
            },
            {
              option: "Maybe",
              image: "https://source.unsplash.com/nss2eRzQwgw/300x300"
            }
          ]
        },
        {
          question: "Great day folks?",
          options: [
            {
              option: "Yeah",
              image: "https://source.unsplash.com/kfJkpeI6Lgc/300x300"
            },
            {
              option: "Bah",
              image: "https://source.unsplash.com/pszENPYeVj4/300x300"
            },
            {
              option: "Top!",
              image: "https://source.unsplash.com/ouyjDk-KdfY/300x300"
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
