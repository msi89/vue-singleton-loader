<template>
  <div class="skeleton" :style="_style"></div>
</template>

<script>
export default {
  name: "Skeleton",
  props: {
    background: String,
    width: { type: [String, Number], default: "100%" },
    height: { type: [String, Number], default: "1em" },
    corner: { type: [String, Number], default: 2 },
    margin: { type: [String, Number], default: 5 },
    mode: { type: String, default: "light" }
  },
  computed: {
    _style() {
      return {
        width: this._width,
        height: this._height,
        margin: this._margin,
        borderRadius: this._corner,
        background: this._background
      };
    },
    _width() {
      return this.isNumeric(this.width) ? `${this.width}px` : this.width;
    },
    _height() {
      return this.isNumeric(this.height) ? `${this.height}px` : this.height;
    },
    _margin() {
      return this.isNumeric(this.margin) ? `${this.margin}px` : this.margin;
    },
    _corner() {
      return this.isNumeric(this.corner) ? `${this.corner}px` : this.corner;
    },
    _background() {
      if (this.background) return this.background;
      return this.mode === "dark" ? "rgba(255, 255, 255, 0.2)" : "#dddbdd";
    }
  },
  methods: {
    isNumeric(value) {
      return /^\d+$/.test(value);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.skeleton {
  position: relative;
  min-height: 20px;
  background: #dddbdd;
  overflow: hidden;
}
.skeleton::after {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  right: 0;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(255, 255, 255, 0.5),
    transparent
  );
  animation: fade 1.3s linear 0.5s infinite;
}

@keyframes fade {
  0% {
    opacity: 0;
    transform: translateX(-100%);
  }
  60% {
    opacity: 1;
    transform: translateX(100%);
  }
  100% {
    opacity: 1;
    transform: translateX(100%);
  }
}
</style>
