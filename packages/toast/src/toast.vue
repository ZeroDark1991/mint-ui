<template>
  <transition name="mint-toast-pop">
    <div class="mint-toast" v-show="visible" :class="customClass">
      <div style="text-align: center">
        <img :src="iconUrl" alt="" style="width: 0.64rem">
      </div>
      <!-- <i class="mint-toast-icon iconfont" :class="iconClass" v-if="iconClass !== ''"></i> -->
      <!-- <div class="mint-toast-icon-back"></div> -->
      <span class="mint-toast-title" :style="{ 'padding-top':  iconClass ? '0.32rem' : '0' }">{{ title }}</span>
      <span class="mint-toast-text" :style="{ 'padding-top':  title ? '0.133333rem' : '0.32rem' }">{{ message }}</span>
    </div>
  </transition>
</template>

<style>
  @component-namespace mint {
    @component toast {
      position: fixed;
      padding: 0.6rem 0.2rem;
      width: 4.266667rem;
      border-radius: 0.133333rem;
      background: rgba(0, 0, 0, 0.7);
      color: #fff;
      box-sizing: border-box;
      text-align: center;
      z-index: 1000;
      transition: opacity .3s linear;
  
      @descendent icon {
        position: absolute;
        left: 0;
        right: 0;
        top: 0.5rem;
        border-radius: 50%;
        text-align: center;
        font-size: 0.64rem !important;
      }
      
      @descendent icon-back {
        display: inline-block;
        border-radius: 50%;
        text-align: center;
        width: 0.5rem;
        height: 0.5rem;
        background: #fff;
        margin-top: .1rem;
      }

      @descendent text {
        font-size: 0.32rem !important;
        color: #dddddd;
        display: block;
        text-align: center;
      }

      @descendent title {
        font-size: 0.48rem !important;
        display: block;
        text-align: center;
      }

      @when placetop {
        top: 50px;
        left: 50%;
        transform: translate(-50%, 0);
      }
      
      @when placemiddle {
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
      }
      
      @when placebottom {
        bottom: 50px;
        left: 50%;
        transform: translate(-50%, 0);
      }
      
      @descendent pop-enter, pop-leave-active {
        opacity: 0;
      }
    }
  }
</style>

<script type="text/babel">
  export default {
    props: {
      message: String,
      title: String,
      className: {
        type: String,
        default: ''
      },
      position: {
        type: String,
        default: 'middle'
      },
      iconClass: {
        type: String,
        default: ''
      },
      iconColor: {
        type: String
      },
      iconUrl: {
        type: String
      }
    },

    data() {
      return {
        visible: false
      };
    },

    computed: {
      customClass() {
        var classes = [];
        switch (this.position) {
          case 'top':
            classes.push('is-placetop');
            break;
          case 'bottom':
            classes.push('is-placebottom');
            break;
          default:
            classes.push('is-placemiddle');
        }
        classes.push(this.className);

        return classes.join(' ');
      }
    }
  };
</script>