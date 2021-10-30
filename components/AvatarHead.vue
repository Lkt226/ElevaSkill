<template>
    <div v-html="Gender === 'male' ? male_head : female_head"/>
</template>

<script>
export default {
    props:{
        Gender: {
            type: String,
            default: 'male'
        },
        Color: {
            type: String,
            default: '#E9CFB8'
        },
        BottomSize: {
            type: Number,
            default: 0
        },
        TopSize: {
            type: Number,
            default: 5
        },
    },
    data() {
        return {
            male_head: 
            `
            <svg width="200" height="250" viewBox="0 0 200 250" fill="none" xmlns="http://www.w3.org/2000/svg">
            <g id="Head">
            <g id="neck">
            <rect id="neck_2" x="70" y="137" width="60" height="100" rx="30" fill="${this.Color}"/>
            <rect id="bottom" x="59" y="55" width="80" height="140" rx="40" fill="black" fill-opacity="0.025"/>
            </g>
            <g id="left ear">
            <rect id="left ear_2" x="20" y="88" width="36" height="45" rx="18" fill="${this.Color}"/>
            <rect id="shadow ear" x="20" y="88" width="36" height="45" rx="18" fill="black" fill-opacity="0.025"/>
            </g>
            <g id="right ear">
            <rect id="right ear_2" x="144" y="88" width="36" height="45" rx="18" fill="${this.Color}"/>
            <rect id="shadow ear_2" x="144" y="88" width="36" height="45" rx="18" fill="black" fill-opacity="0.025"/>
            </g>
            <rect id="bottom" x="${55 - this.BottomSize/2}" y="50" width="${90 + this.BottomSize}" height="140" rx="50" fill="${this.Color}"/>
            <rect id="top" x="32" y="12" width="136" height="${165 + this.TopSize}" rx="70" fill="${this.Color}"/>
            <path id="Vector 42" d="M99 134C103.971 134 108 125 108 125C108 125 102.576 126.688 99 126.688C95.424 126.688 90 125 90 125C90 125 94.0294 134 99 134Z" fill="black" fill-opacity="0.025"/>
            </g>
            </svg>
            `,
        }
    }
}
</script>

<style>

</style>


