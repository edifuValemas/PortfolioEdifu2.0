<template>
  <div class="canvas">
    <div id="totalCounter" class="total-counter"></div>

    <div id="clap" class="clap-container">
      <img class="clap-icon" src="~assets/clap.svg" alt="clap icon" />
    </div>

    <div id="clicker" class="click-counter">
      <span class="counter"></span>
    </div>

    <div id="sonar-clap" class="clap-container-sonar"></div>

    <div id="particles" class="particles-container">
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
      
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
    </div>

    <div id="particles-2" class="particles-container">
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
    </div>

    <div id="particles-3" class="particles-container">
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
      <div class="triangle">
        <div class="square"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // methods: {
  //   onClick: function() {
  //     alert('ok')
  //   }
  // }
}
</script>

<style scoped lang="css">
.canvas {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 300px;
  height: 300px;
  position: relative;
  padding: 0px 0px 0px 0px;
}
.canvas .total-counter {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  position: absolute;
  margin-top: -45px;
  color: gray;
  font-family: sans-serif;
  font-size: 16px;
}
.canvas .total-counter.fader {
  animation: fade-in 1400ms forwards;
}
.canvas .clap-container {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  width: 70px;
  height: 70px;
  border: 1px solid #fc3a52;
  border-radius: 50%;
  z-index: 2;
  background: #f6ecdd;
  cursor: pointer;
}
.canvas .clap-container .clap-icon {
  font-size: 30px;
  color: var(--primary-color);
  height: 40px;
}
.canvas .clap-container:hover {
  border: 1px solid var(--primary-color);
}
.canvas .clap-container.scale {
  animation: scaleAndBack 700ms forwards;
}
.canvas .click-counter {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 35px;
  height: 35px;
  position: absolute;
  top: 132px;
  background-color: var(--primary-color);
  border-radius: 50%;
  z-index: 1;
}
.canvas .click-counter .counter {
  font-family: sans-serif;
  font-size: 14px;
  color: #fff;
}
.canvas .click-counter.first-active {
  animation: first-bump-in 1s forwards;
}
.canvas .click-counter.active {
  animation: bump-in 1s forwards;
}
.canvas .clap-container-sonar {
  width: 60px;
  height: 60px;
  background: var(--primary-color);
  border-radius: 50%;
  position: absolute;
  opacity: 0;
  z-index: 0;
}
.canvas .hover-active {
  animation: sonar-wave 2s forwards;
}
.canvas .particles-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 60px;
  height: 60px;
  position: absolute;
  /* border: 1px solid gray; */
  /* z-index: 3; */
}
.canvas .particles-container .triangle {
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 10px solid red;
  border-bottom: 4px solid transparent;
  position: absolute;
}
.canvas .particles-container .triangle .square {
  width: 5px;
  height: 5px;
  background: var(--primary-color);
  position: absolute;
  left: -15px;
  top: 0;
}
.canvas .particles-container .pop-top {
  animation: pop-top 1s forwards;
}
.canvas .particles-container .pop-top-left {
  animation: pop-top-left 1s forwards;
}
.canvas .particles-container .pop-top-right {
  animation: pop-top-right 1s forwards;
}
.canvas .particles-container .pop-bottom-right {
  animation: pop-bottom-right 1s forwards;
}
.canvas .particles-container .pop-bottom-left {
  animation: pop-bottom-left 1s forwards;
}

@keyframes sonar-wave {
  0% {
    opacity: 0.7;
  }
  100% {
    transform: scale(1.4);
    opacity: 0;
  }
}
@keyframes fade-in {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes pop-top {
  0% {
    transform: translate(0, 0) rotate(0);
    opacity: 0.4;
  }
  100% {
    transform: translate(0, -100px) rotate(0);
    opacity: 0;
  }
}
@keyframes pop-top-left {
  0% {
    transform: translate(0, 0) rotate(-55deg);
    opacity: 0.4;
  }
  100% {
    transform: translate(-100px, -50px) rotate(-55deg);
    opacity: 0;
  }
}
@keyframes pop-top-right {
  0% {
    transform: translate(0, 0) rotate(55deg);
    opacity: 0.4;
  }
  100% {
    transform: translate(100px, -50px) rotate(55deg);
    opacity: 0;
  }
}
@keyframes pop-bottom-right {
  0% {
    transform: translate(0, 0) rotate(135deg);
    opacity: 0.4;
  }
  100% {
    transform: translate(70px, 80px) rotate(135deg);
    opacity: 0;
  }
}
@keyframes pop-bottom-left {
  0% {
    transform: translate(0, 0) rotate(-135deg);
    opacity: 0.4;
  }
  100% {
    transform: translate(-70px, 80px) rotate(-135deg);
    opacity: 0;
  }
}
@keyframes first-bump-in {
  0% {
    transform: translateY(-65px);
    opacity: 1;
  }
  50% {
    transform: translateY(-80px);
    opacity: 1;
  }
  100% {
    transform: translateY(-100px);
    opacity: 0;
  }
}

@keyframes bump-in {
  0% {
    transform: translateY(-80px) scale(0.9);
    opacity: 1;
  }
  50% {
    transform: translateY(-80px) scale(1);
    opacity: 1;
  }
  100% {
    transform: translateY(-100px) scale(1);
    opacity: 0;
  }
}
@keyframes scaleAndBack {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.15);
  }
  100% {
    transform: scale(1);
  }
}
</style>