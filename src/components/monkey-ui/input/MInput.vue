<template>
    <div
    :class="[
    'm-input--wrapper',
    'm-input-' + (size || 'default'),
    ]"><input
        v-model="input"
        :placeholder="placeholder"
        :class="['m-input--inner']"
        :tabindex="tabindex"
        :maxlength="maxlength"
        :minlength="minlength"
    /></div>
</template>

<script>
export default {
    props: {
        value: undefined,
        placeholder: String,
        size: String,
        tabindex: Number,
        maxlength: Number,
        minlength: Number,
    },
    computed: {
        input: {
            get() {
                return this.value
            },
            set(newVal) {
                this.$emit('input', newVal);
            }
        }
    }
}
</script>

<style scoped>
div.m-input--wrapper input.m-input--inner {
    border: 0;
    outline: 0;
    margin: 0;
    border-radius: 4px;
    border: solid 1px #dcdfe6;
    font-size: 14px;
    line-height: 40px;
    height: 40px;
    box-sizing: border-box;
    padding: 0 8px;
    width: 100%;
}

div.m-input--wrapper input.m-input--inner:focus {
    border-color: rgba(45,140,240, 1);
    box-shadow: rgba(45,140,240, .3) 0 0 0 3px;
}

div.m-input--wrapper.m-input-default input.m-input--inner {
    line-height: 32px;
    height: 32px;
}

div.m-input--wrapper.m-input-small input.m-input--inner {
    line-height: 24px;
    height: 24px;
}
</style>