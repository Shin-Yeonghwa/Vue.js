<template>
    <button 
        :type="buttonType" 
        :class="[
            $style[buttonType],
            $style[colorType]
        ]"
    >
        <!-- {{ title }} -->
        <slot></slot>
    </button>
</template>

<script>
    export default {
        name: 'BaseButton',
        props:{
            buttonType: {
                type: String,
                default: 'button'
            },
            colorType: {
                type: String,
                default: 'translucence'
            }
        }
    }

</script>

<style lang="scss" module>
    .button {
        display: inline-block;
        height: 52px;
        padding: 0 24px;
        border:0;
        font-size: 18px;
        appearance: none;
        -webkit-appearance: none;
        box-sizing: border-box;
        }

        .translucence {
        color: #000;
        border: 0;
        background: rgba(255, 255, 255, 0.7);
        }

        .white_outline {
        color: #fff;
        border: 1px solid #fff;
        background: rgba(255, 255, 255, 0);
    }
</style>