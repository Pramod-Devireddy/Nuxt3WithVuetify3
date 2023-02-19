<template>
    <div>
        <div id="element-to-convert">
            <p>Count: {{ count }}</p>
            <button @click="incrementCount">Increment Count</button>
            <p>Reversed Message: {{ reversedMessage }} + {{ reversedText }}</p>
            <input v-model="message" />
            <h1 style="background-color: blueviolet; color: aliceblue;">ok</h1>
            <img src="https://img-19.commentcamarche.net/cI8qqj-finfDcmx6jMK6Vr-krEw=/1500x/smart/b829396acc244fd484c5ddcdcb2b08f3/ccmcms-commentcamarche/20494859.jpg"
                alt="Trulli" width="500" height="333">
            <img src="https://www.w3schools.com/html/pic_trulli.jpg" crossOrigin="anonymous">

            <h1 style="background-color: blueviolet; color: aliceblue;">ok</h1>
        </div>
        <button @click="exportToPDF">Export to PDF</button>
    </div>
</template>

<script>
import html2pdf from "html2pdf.js";

export default {

    data () {
        return {
            count: 0,
            message: "Hello, Vue!",
            text: "",
            hasAccessedReversedMessage: false // new flag
        };
    },

    methods: {
        incrementCount () {
            this.count++;
        },

        decrementCount () {
            this.count--;
        },

        exportToPDF () {
            html2pdf(document.getElementById("element-to-convert"), {
                margin: 1,
                filename: "i-was-html.pdf",
                image: { type: 'png', quality: 1 },
                html2canvas: { useCORS: true, scale: 1 },
            });
        },
    },

    computed: {
        reversedMessage () {
            if (!this.hasAccessedReversedMessage) {
                this.hasAccessedReversedMessage = true;
                this.incrementCount(); // increment count the first time reversedMessage is accessed
            }
            return this.message.split("").reverse().join("");
        },

        reversedText () {
            return this.text.split("").reverse().join("");
        }
    },

    watch: {
        reversedMessage () {
            this.incrementCount();
        }
    }
};
</script>
  