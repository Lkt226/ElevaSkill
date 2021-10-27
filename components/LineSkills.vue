<template>
    <div class="line-text">
        <h3 class="text">
        {{this.text}}

        <label :for="type" class="openbyID">
            <input
                type="checkbox"
                :id="type"
                :name="type"
                class="invisible openbyID"
                checked
            />
            <img @click="clickIsOpen" class="open-button" src="../static/open.svg" alt="open"/>
        </label>
        </h3>
        <ul v-if="isOpen === true">
            <li class="text item" v-for="(item, index) in api" :key="index">
                <h4 class="text c-gray">{{`${item.name}${item[extra] ? " - "+item[extra] : ""}`}}</h4>
                <h4 class="c-red"> - </h4>
            </li>
            <li class="text item">
                <h4 class="text c-gray"> Adicionar skill ...</h4>
                <h4 class="c-green"> + </h4>
            </li>
        </ul>
        <Divider/>
    </div>
</template>

<script>
export default {
    props:['text', 'api', 'type', 'extra'],
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
    .openbyID:checked ~ .open-button{
        transform: rotateZ(180deg);
    }

</style>