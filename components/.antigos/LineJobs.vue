<template>
    <div>
        <h3 class="text" style="padding-left: 0.5rem;">
            Vagas
            <label for="line-jobs" class="openbyID">
            <input
                type="checkbox"
                id="line-jobs"
                name="line-jobs"
                checked
                class="invisible openbyID"
            />
                <img @click="clickIsOpen" class="open-button" src="../static/open.svg" alt="open"/>
            </label>
            <img class="enter-button" src="../static/open.svg" alt="open"/>
        </h3>
            <Divider type="l" pad="1"/>

        <ul v-if="isOpen === true" class="line-text">
            <li v-for="(item, index) in api" :key="index">
                <span class="text-job">
                    <h3 class="c-gray">{{item.name}}</h3>
                    <h4 class="c-gray">{{item.createDate}}</h4>
                </span>
                <Divider/>
                <h4>{{`${item.company} | ${item.seniority}`}}</h4>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props:['text', 'api'],
    data() {
        return {
            isOpen: true,
        }
    },
    methods: {
        clickIsOpen(){
            this.isOpen = !this.isOpen;
        },
    }
}
</script>

<style scoped>
    .line-text{
        padding: 0 1rem;   
    }

    .text{
        display: flex;
        justify-content: space-between;
    }
    
    .text-job{
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
    }

    .item{
        padding: 1rem 0rem 0.2rem;
    }

    .invisible{
        display:none;
        opacity: 0;
    }
    .enter-button{
        transform: rotateZ(-90deg);
    }
    .openbyID{
        margin-right: auto;
        padding-left: 1rem;
    }
    .openbyID:checked ~ .open-button{
        transform: rotateZ(180deg);
    }

</style>