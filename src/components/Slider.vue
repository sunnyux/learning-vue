<template>
    <div class="slider-container">
        <input type="range" class="slider" id="mySlider"
               :value="value"
               @input="$emit('input', $event.target.value)"
               step="step" min="min" max="max">
        <!--               :value="value" @input="valueChange($event.target.value)"-->

    </div>
</template>

<script>
    export default {
        name: "Slider",
        props: {
            value: {
                type: Number,
                default: 10
            },
            step: {
                type: Number,
                default: 1
            },
            min: {
                type: Number,
                default: 1
            },
            max : {
                type: Number,
                default: 100
            }
        },
        methods: {
            valueChange(v) {
                console.log("value changed to ", v);
                this.value = v;
            }
        }
    }
</script>

<style scoped>
    .slider-container {
        width: 100%; /* Width of the outside container */
    }

    /* The slider itself */
    .slider {
        -webkit-appearance: none; /* Override default CSS styles */
        appearance: none;
        border-radius: 5px;
        width: 100%; /* Full-width */
        height: 10px; /* Specified height */
        background: #d3d3d3; /* Grey background */
        outline: none; /* Remove outline */
        opacity: 0.7; /* Set transparency (for mouse-over effects on hover) */
        -webkit-transition: .2s; /* 0.2 seconds transition on hover */
        transition: opacity .2s;
        margin-bottom: 10px;
        margin-top: 10px;
    }

    /* Mouse-over effects */
    .slider:hover {
        opacity: 1; /* Fully shown on mouse-over */
    }

    /* The slider handle (use -webkit- (Chrome, Opera, Safari, Edge) and -moz- (Firefox) to override default look) */
    .slider::-webkit-slider-thumb {
        -webkit-appearance: none; /* Override default look */
        appearance: none;
        width: 25px; /* Set a specific slider handle width */
        height: 25px; /* Slider handle height */
        border-radius: 50%;
        background: #4CAF50; /* Green background */
        cursor: pointer; /* Cursor on hover */
    }

    .slider::-moz-range-thumb {
        width: 25px; /* Set a specific slider handle width */
        height: 25px; /* Slider handle height */
        background: #4CAF50; /* Green background */
        /*border-radius: 50%;*/
        cursor: pointer; /* Cursor on hover */
    }

</style>