<template>
    <div class="line-text">
        <h3 class="text">
        {{this.title}}

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
            <li class="item" v-for="(item, index) in api" :key="index">
                <span class="text">
                    <h4 class="c-gray">{{`${item.name}${item[extra] ? " - "+item[extra] : ""}`}}</h4>
                    <h4 class="c-red"> - </h4>
                </span>
                <Divider/>
                <h4 class="c-gray">{{item.title}} | {{item.start_date}} - {{item.end_date}} </h4>
                <Divider/>
                <h4 class="c-gray">{{item.description}}</h4>
                <Divider/>
            </li>
            <li class="item">
                <span class="text">
                    <h4 class="c-gray"> Adicionar experiência ...</h4>
                    <h4 class="c-green"> + </h4>
                </span>
                <Divider/>
                <h4 class="c-gray">Cargo | inicio - fim </h4>
                <Divider/>
                <h4 class="c-gray">O que você fazia na empresa?</h4>
            </li>
        </ul>
        <Divider/>
    </div>
</template>

<script>
export default {
    props:['title', 'api', 'type'],
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