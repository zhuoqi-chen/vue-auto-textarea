<template>
    <div :placeholder="placeholder" class="editable" contenteditable="true" @input="update"></div>
</template>

<script>
export default {
  name: "x-editable",
  props: {
    placeholder: {
      type: String,
      default: "请输入内容"
    },
    value: {
      type: String,
      default: ""
    }
  },
  mounted: function() {
    this.$el.innerText = this.value;
    this.$on("clean", () => {
      this.$el.innerText = "";
    });
  },
  methods: {
    update(event) {
      this.$emit("input", event.target.innerText);
    }
  }
};
</script>
<style lang="css">
.editable {
  box-sizing: border-box;
  position: relative;
  cursor: text;
  width: 100%;
  border: 1px #e5e5e5 solid;
  padding: 10px;
  outline: none;
  background: white;
  border-radius: 5px;
}
.editable:empty:before {
  position: absolute;
  height: 22px;
  top: 10px;
  content: attr(placeholder);
  color: #878787;
  display: block; /* For Firefox */
}
</style>
