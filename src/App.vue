<template>
    <div class="content">
      <div class="header">
        <div class="header-content">
          <i class="fa-solid fa-chevron-left"></i>
          <h2>RGB WI-FI люстра<br>
            <span>расположение «кухня»</span></h2>
          <i class="fa-solid fa-gear"></i>
        </div>
      </div>
      <color-picker v-bind="color" @input="onInput"/>
      <div class="color-wrap">
        <div class="color" @click="click" style="background: #00ffff"></div>
        <div class="color" @click="click1" style="background: red"></div>
        <div class="color" @click="click2" style="background: #0000FF"></div>
        <div class="color" @click="click3" style="background: #BF00FF"></div>
        <div class="color" @click="click4" style="background: yellow"></div>
        <div class="color" @click="click5" style="background: orange"></div>
        <div class="color" @click="click6" style="background: #00FF00"></div>
        <div class="color" @click="click7" style="background: #8000FF"></div>
      </div>
      <div class="range_1">
        <svg fill="#FFFFFF" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32" width="32px" height="32px">
          <path
              d="M 15 3 L 15 8 L 17 8 L 17 3 Z M 7.5 6.09375 L 6.09375 7.5 L 9.625 11.0625 L 11.0625 9.625 Z M 24.5 6.09375 L 20.9375 9.625 L 22.375 11.0625 L 25.90625 7.5 Z M 16 9 C 12.144531 9 9 12.144531 9 16 C 9 19.855469 12.144531 23 16 23 C 19.855469 23 23 19.855469 23 16 C 23 12.144531 19.855469 9 16 9 Z M 16 11 C 18.773438 11 21 13.226563 21 16 C 21 18.773438 18.773438 21 16 21 C 13.226563 21 11 18.773438 11 16 C 11 13.226563 13.226563 11 16 11 Z M 3 15 L 3 17 L 8 17 L 8 15 Z M 24 15 L 24 17 L 29 17 L 29 15 Z M 9.625 20.9375 L 6.09375 24.5 L 7.5 25.90625 L 11.0625 22.375 Z M 22.375 20.9375 L 20.9375 22.375 L 24.5 25.90625 L 25.90625 24.5 Z M 15 24 L 15 29 L 17 29 L 17 24 Z"/>
        </svg>
        <input type="range" class="range" min="20" max="200" v-model="color.luminosity" id="weight">
        <svg fill="#FFFFFF" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32" width="32px" height="32px">
          <path
              d="M 15 3 L 15 8 L 17 8 L 17 3 Z M 7.5 6.09375 L 6.09375 7.5 L 9.625 11.0625 L 11.0625 9.625 Z M 24.5 6.09375 L 20.9375 9.625 L 22.375 11.0625 L 25.90625 7.5 Z M 16 9 C 12.144531 9 9 12.144531 9 16 C 9 19.855469 12.144531 23 16 23 C 19.855469 23 23 19.855469 23 16 C 23 12.144531 19.855469 9 16 9 Z M 16 11 C 18.773438 11 21 13.226563 21 16 C 21 18.773438 18.773438 21 16 21 C 13.226563 21 11 18.773438 11 16 C 11 13.226563 13.226563 11 16 11 Z M 3 15 L 3 17 L 8 17 L 8 15 Z M 24 15 L 24 17 L 29 17 L 29 15 Z M 9.625 20.9375 L 6.09375 24.5 L 7.5 25.90625 L 11.0625 22.375 Z M 22.375 20.9375 L 20.9375 22.375 L 24.5 25.90625 L 25.90625 24.5 Z M 15 24 L 15 29 L 17 29 L 17 24 Z"/>
        </svg>
      </div>
      <div class="range_1">
        <i class="fa-solid fa-snowflake"></i>
        <input type="range" class="range background" min="20" max="200" v-model="color.saturation" id="weight">
        <i class="fa-sharp fa-solid fa-fire-flame-curved"></i>
      </div>
      <!--        <h1 v-text="msg"></h1>-->
      <!--        <pre v-text="JSON.stringify(color, null, 4)"></pre>-->
    </div>

    <div class="popupp"></div>
    <div class="popup-container">
      <div class="popup-content">
        <div class="text">
          <h1>Дополнительные насстройки</h1>

          <div class="checkbox">
            <div class="radio">
              <input type="checkbox" id="toggle" class="toggle-item">
              <label for="toggle"></label>
            </div>
            <h2 class="check">плавный переход</h2>
          </div>
          <div class="selected">
            <select>
              <option>световые эффекты</option>
              <option>световые</option>
              <option>эффекты</option>
            </select>
          </div>
        </div>
    </div>
  </div>

</template>

<script>
import ColorPicker from '../src/ColorPicker.vue';

export default {
  components: {ColorPicker},
  data() {
    return {
      color1: '',
      color: {
        hue: 50,
        saturation: 100,
        luminosity: 50,
        alpha: 1,
      },
    };
  },
  methods: {
    onInput(hue) {
      this.color.hue = hue;
    },
    click() {
      this.color.hue = 180
    },
    click1() {
      this.color.hue = 0
    },
    click2() {
      this.color.hue = 240
    },
    click3() {
      this.color.hue = 285
    },
    click4() {
      this.color.hue = 60
    },
    click5() {
      this.color.hue = 45
    },
    click6() {
      this.color.hue = 120
    },
    click7() {
      this.color.hue = 270
    },
  },
  mounted() {
    let body = document.querySelector('#app')
    let radio = document.querySelector('.toggle-item')
    let popupp = document.querySelector('.popupp')
    let popup_container = document.querySelector('.popup-container')
    let popup_content = document.querySelector('.popup-content')
    let fa_gear = document.querySelector('.fa-gear')
    let check = document.querySelector('.check')
    let text = document.querySelector('.text h1')
    popupp.style.display = 'none'
    popup_container.style.display = 'none'

    fa_gear.addEventListener('click', () => {
      popupp.style.display = 'block'
      popup_container.style.display = 'block'
    })

    radio.addEventListener('change',() => {
      body.classList.toggle('color1')
      popup_container.classList.toggle('color1')
      popupp.classList.toggle('opacity')
      popup_content.classList.toggle('color34')
      check.classList.toggle('colore')
      text.classList.toggle('colore')
    })

    window.addEventListener('load', function(){

      var touchsurface = document.querySelector('.popup-container'),
          startX,
          startY,
          dist,
          threshold = 150, //required min distance traveled to be considered swipe
          allowedTime = 200, // maximum time allowed to travel that distance
          elapsedTime,
          startTime

      function handleswipe(isrightswipe){
        if (isrightswipe)
          touchsurface.innerHTML = 'Congrats, you\'ve made a <span style="color:red">right swipe!</span>'
        else{
          touchsurface.innerHTML = 'Condition for right swipe not met yet'
        }
      }

      touchsurface.addEventListener('touchstart', function(e){
        touchsurface.innerHTML = ''
        var touchobj = e.changedTouches[0]
        dist = 0
        startX = touchobj.pageX
        startY = touchobj.pageY
        startTime = new Date().getTime() // record time when finger first makes contact with surface
        e.preventDefault()
      }, false)

      touchsurface.addEventListener('touchmove', function(e){
        e.preventDefault() // prevent scrolling when inside DIV
      }, false)

      touchsurface.addEventListener('touchend', function(e){
        var touchobj = e.changedTouches[0]
        dist = touchobj.pageX - startX // get total dist traveled by finger while in contact with surface
        elapsedTime = new Date().getTime() - startTime // get time elapsed
        // check that elapsed time is within specified, horizontal dist traveled >= threshold, and vertical dist traveled <= 100
        var swiperightBol = (elapsedTime <= allowedTime && dist >= threshold && Math.abs(touchobj.pageY - startY) <= 100)
        handleswipe(swiperightBol)
        e.preventDefault()
      }, false)

    }, false) // end window.onload
  },
};
</script>
<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: #ffff;
  font-family: sans-serif;
}

#app {
  background: #0e2142;
  height: 99vh;
}

.background_2 {
  background: #fff;
}

.popupp {
  width: 100%;
  height: 100vh;
  background: #000;
  opacity: .7;
  position: absolute;
  bottom: 0;
}
.colore {
  color: #ffff!important;
}
input {
  display: block;
  margin: 20px 0;
}

.content {
  z-index: 0;
}
.color34 {
  background: #000!important;
  color: #fff;
}
.popup-content {
  background: #fff;
  border-radius: 30px;
  height: 252px;
  padding: 30px;
}

select, option {
  color: #000 !important;
  width: 390px;
  padding: 0 17px;
  height: 46px;
}

.selected {
  display: flex;
  justify-content: center;
  align-items: center;
}

.checkbox {
  display: flex;
  align-items: center;
  height: 15vh;
  margin: 0 22px;
}

.popup-container {
  z-index: 99;
  position: relative;
  bottom: 67px;
  background: transparent !important;
}

.color2 {
  background: #fff;
}

.checkbox h2 {
  font-size: 19px;
  color: #3d3c3c;
  margin: 0 15px;
  font-weight: 400;
}

.text h1 {
  font-size: 22px;
  color: #000;
  text-align: center;
}

.background {
  background: rgb(230, 151, 23) !important;
  background: linear-gradient(233deg, rgba(230, 151, 23, 1) 38%, rgba(43, 191, 215, 1) 53%) !important;
}

.header-content {
  display: flex;
  align-items: center;
  margin: 0 0 50px;
}

.range_1 svg, img {
  width: 18px;
}

.range_1 {
  display: flex;
  align-items: center;
  font-size: 12px;
  margin: 0 0 20px;
}

.range_1 input {
  margin: 0 6px;
}

.header-content h2 {
  font-size: 17px;
  margin: 0 50px;
  font-weight: 700;
  text-align: center;
}

.header-content h2 span {
  font-size: 12px;
  text-align: center;
  font-weight: 400;
}

*,
*:before,
*:after {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.rcp, .rcp div, .rcp button {
  border: none !important;
}

.color {
  color: #000 !important;
}

.color1 {
  background: #ffffff;
}
.opacity {    background: #fff;
}

.rcp__well {
  position: absolute;
  width: 74%;
  height: 73%;
  top: 13.5%;
  font-size: 34px;
  left: 13%;
  padding: 0;
  margin: 0;
  border-radius: 50%;
  outline: 0;
  cursor: pointer;
  border: none !important;
  background: #000;
}

.fa-sharp {
  color: red;
  fill: red
}

.container {
  background-color: #ffffff;
  padding: 40px 30px;
  width: 50%;
  min-width: 400px;
  position: absolute;
  transform: translate(-50%, -50%);
  top: 50%;
  left: 50%;
  border-radius: 5px;
  font-family: 'Poppins', sans-serif;
  box-shadow: 25px 25px 30px rgba(0, 0, 0, 0.15);
}

.row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 40px;
}

.row span {
  font-weight: 500;
}

input[type="range"] {
  width: 100%;
  height: 2px;
  -webkit-appearance: none;
  appearance: none;
  background: rgb(255, 255, 255);
  background: linear-gradient(233deg, rgba(255, 255, 255, 1) 35%, rgba(0, 0, 0, 1) 52%);
  border-radius: 3px;
  outline: none;
}

input[type="range" i] {
  color: #fff !important;
}

input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  height: 15px;
  border: 2px solid #437fd0;
  width: 15px;
  background-color: #fff;
  border-radius: 50%;
  cursor: pointer;
}

#result {
  font-size: 30px;
  font-weight: 700;
  letter-spacing: 1px;
  text-align: center;
  color: #0be881;
}

#category {
  font-size: 18px;
  text-align: center;
  letter-spacing: 1px;
}

.toggle-item + label {
  display: flex;
  width: 5em;
  height: 2em;
  background: #9595ff;
  opacity: .7;
  border: none;
  border-radius: 8px;
  position: relative;
  transition: all .3s ease;
  cursor: pointer;
  box-shadow: inset 0 0 5px #222;
}

.toggle-item + label:after {
  content: '';
  position: absolute;
  width: 1.5em;
  height: 1.5em;
  background: #000;
  border-radius: 20%;
  top: 0.25em;
  left: 0.25em;
  transition: all .2s ease;
}

.toggle-item:checked + label {
  background: #fff;
}

.toggle-item:checked + label:after {
  left: 3.1em;
}

.toggle-item:checked  ~ .back{
  background: yellow;
}

.btn[disabled] {
  cursor: not-allowed;
}

.fa-solid {
  cursor: pointer !important;
}

.btn-wrapper button {
  width: 200px;
  padding: 15px;
  border: none;
  border-radius: 3px;
  background: deepskyblue;
  margin: 10px 30px 30px;
}

#toggle {
  display: none;
}

.content {
  width: 15%;
  margin: 0 auto;
  padding: 40px 0;
}

@media (max-width: 600px) {
  input[type="range"] {
    width: 82%;
  }

  .content {
    width: 55%;
  }

  .header-content h2 {
    margin: 0 47px;
    font-size: 15px;
    font-weight: 700;
  }

  .header-content h2 span {
    font-size: 11px;
    text-align: center;
    font-weight: 400;
  }

  .color {
    height: 23px;
  }


}
</style>
