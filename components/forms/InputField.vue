<template>
  <div class="st-textfield">
    <input
      :id="id"
      v-model="internalValue"
      :class="{ active: inputText }"
      :type="type"
      :name="name"
      :placeholder="placeholder"
      :required="required"
      :aria-required="required"
    >
    <label :for="id">
      {{ label }}
      <span
        v-if="required === true"
        class="st-required"
      >
        必須
      </span>
    </label>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Emit } from 'nuxt-property-decorator'
@Component
class InputField extends Vue {
  @Prop({ type: String }) value
  @Prop({ type: String }) id
  @Prop({ type: String, default: 'text' }) type
  @Prop({ type: String }) name
  @Prop({ type: Boolean, default: false, required: false }) required
  @Prop({ type: String, default: '' }) placeholder
  @Prop({ type: String, required: true }) label
  // data
  valued: string = ''
  // emit
  @Emit()
  input (value: string) {
    return value
  }
  // computed
  get internalValue (): string {
    return this.valued
  }
  set internalValue (newVal: string) {
    this.valued = newVal
    this.input(newVal)
  }
  get inputText (): boolean {
    if (this.valued.length > 0) {
      return true
    }
    return false
  }
}
export default InputField
</script>

<style lang="scss" scoped>
.st-textfield {
  height: 56px;
  position: relative;
  text-align: left;
  input,
  textarea,
  select {
    width: 100%;
    height: 100%;
    border: 1px solid #707070;
    border-radius: 4px;
    padding: 0 16px;
    background-color: #fff;
    font-size: 16px;
  }
  textarea {
    padding: 16px;
    line-height: 1.5;
  }
  label {
    position: absolute;
    left: 12px;
    top: 16px;
    font-size: 14px;
    color: #707070;
    transition: 0.2s all;
    padding: 0 4px;
  }
  input.active,
  textarea.active,
  select.active {
    + label{
      transform: translateY(-24px);
      font-size: 12px;
      color: #ffa952;
      &::before{
        content: '';
        width: 100%;
        height: 1px;
        background-color: #fff;
        position: absolute;
        left: 0;
        top: 47%;
        z-index: -1;
      }
    }
  }
  input:focus,
  textarea:focus,
  select:focus {
    border: 1px solid #ffa952;
    outline: none;
    + label {
      transform: translateY(-24px);
      font-size: 12px;
      color: #ffa952;
      &::before {
        content: '';
        width: 100%;
        height: 1px;
        background-color: #fff;
        position: absolute;
        left: 0;
        top: 47%;
        z-index: -1;
      }
    }
  }
}
</style>
