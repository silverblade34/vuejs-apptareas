<template>
    <main>
        <div class="tarjetas-container">
            <div class="tarjetas" v-for="tarjeta in boards" :key="tarjeta.id">
                <h5>{{ tarjeta.name }}</h5>
                <InputNew @on-new-item="(text) => handleNewItem(text, tarjeta)" />
                <div class="list-items">
                    <li v-for="item in tarjeta.items" :key="item.id">{{ item.name }}</li>
                </div>
            </div>
        </div>
    </main>
</template>

<script setup>
import { reactive } from 'vue';
import InputNew from '../components/InputNew.vue'

let boards = reactive([
    {
        id: crypto.randomUUID,
        name: "Tarjeta 1",
        items: [
            {
                id: crypto.randomUUID,
                name: "Item 1"
            },
            {
                id: crypto.randomUUID,
                name: "Item 2"
            },
            {
                id: crypto.randomUUID,
                name: "Item 3"
            }
        ]
    },
    {
        id: crypto.randomUUID,
        name: "Tarjeta 2",
        items: [
            {
                id: crypto.randomUUID,
                name: "Item 11"
            },
            {
                id: crypto.randomUUID,
                name: "Item 22"
            },
            {
                id: crypto.randomUUID,
                name: "Item 33"
            }
        ]
    }
])

function handleNewItem(text, tarjeta) {
    tarjeta.items.push({
        id: crypto.randomUUID,
        name: text
    })

}
</script>

<style scoped lang="scss">
main {
    display: flex;
    justify-content: center;
    width: 100%;
    padding: 2rem;

    .tarjetas-container {
        display: flex;
        gap: 20px;

        .tarjetas {
            padding: 0.5rem 2rem;
            border-radius: 10px;
            color: white;
            background-color: rgb(255, 108, 108);

            div {
                list-style: none;
                min-height: 100px;
                padding: 4px 0;
                box-sizing: border-box;
                li {
                    cursor: pointer;
                    min-width: 6rem;
                    text-align: center;
                    padding: 0.2rem 0.3rem;
                    border-radius: 5px;
                    margin-bottom: 4px;
                    background-color: #575757;
                }
            }
        }
    }
}
</style>