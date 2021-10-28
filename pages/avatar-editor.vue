<template>
    <div id="avatar-editor">
        {{onChange}}
        <div id="avatar">
            <img src="../static/avatar-itens/glass.svg" alt="">
            <div id="avatar-head" style="z-index: -1"/>
        </div>
        <div id="editor" v-html="getConfig()"/>
    </div>
</template>

<script>
const currentColor = "#E9CFB8" 
const headSizes = {
    'head-top': 0,
    'head-bottom': 0
}
export default {
    data() {
        return {
            currentColor,
            configs: {
                'head-top'(){return `<rect id="head-top" x="13" width="140" height="${165 + headSizes['head-top']}" rx="70" fill="${currentColor}"/>`},
                'head-bottom'(){return `<rect id="head-bottom" x="${33 - headSizes['head-bottom']/2}" y="45" width="${100 + headSizes['head-bottom']}" height="140" rx="50" fill="${currentColor}"/>`},
            },
        }
    },
    methods: {
        changeColor(color) {
            currentColor = color||'#E9CFB8';
        },
        getAvatar() {
            return `
            <svg width="200" height="250" viewBox="0 0 166 225" fill="none" xmlns="http://www.w3.org/2000/svg">
                <g id="Head">
                <g id="neck">
                <rect id="neck_2" x="53" y="125" width="60" height="100" rx="30" fill="${this.currentColor}"/>
                <rect id="shodow neck" x="53" y="125" width="60" height="100" rx="30" fill="black" fill-opacity="0.025"/>
                </g>
                <g id="left ear">
                <rect id="left ear_2" y="76" width="36" height="45" rx="18" fill="${this.currentColor}"/>
                <rect id="shadow ear" y="76" width="36" height="45" rx="18" fill="black" fill-opacity="0.025"/>
                </g>
                <g id="right ear">
                <rect id="right ear_2" x="130" y="76" width="36" height="45" rx="18" fill="${this.currentColor}"/>
                <rect id="shadow ear_2" x="130" y="76" width="36" height="45" rx="18" fill="black" fill-opacity="0.025"/>
                </g>
                ${this.configs['head-bottom']()}
                ${this.configs['head-top']()}
                </g>
            </svg>
            `
        },
        getConfig(){
            let configList = "";
            for (const config in this.configs) {
                const textConfig = "range_"+config
                configList += `<input type="range" name="${textConfig}" id="${textConfig}">`
            }
            return configList;
        },
        refresh() {
            const doc = document.getElementById('avatar-head');
            doc.innerHTML = this.getAvatar();
        }
    },
    computed: {
        onChange() {
            setInterval(() => {
                for (const config in this.configs) {
                const textConfig = "range_"+config
                    try {
                        const doc = document.getElementById(textConfig)
                        const value = doc.value/5
                        if(headSizes[config] !== value){ 
                            headSizes[config] = value
                            this.refresh()
                        }
                    } catch (error) {
        
                    }
                }
            }, 100);
        },
    }
}
</script>

<style scoped>
#avatar-editor {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
#avatar > *{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}


</style>