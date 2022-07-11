<script setup>
import { ref, computed } from "vue";
import { useFetch } from "./hooks/fetch";

import Title from "./components/Title.vue";
import Button from "./components/Button.vue";

const counter = ref(0);
// const user = ref({});
const { data, error } = useFetch(
    "https://jsonplaceholder.typicode.com/todos/1"
);

const increment = () => {
    counter.value++;
};

const counterPorDos = computed(() => {
    return counter.value * 2;
});

// fetch("https://jsonplaceholder.typicode.com/todos/1")
//     .then((response) => response.json())
//     .then((data) => {
//         user.value = data;
//     });
</script>

<template>
    <Title text="Texto dinámico" />
    <p>{{ counterPorDos }}</p>
    <h3>{{ data?.title }}</h3>
    <Button :counter="counter" @increment="increment" />
</template>

<!-- <script>
import { ref, computed } from "vue";
export default {
    setup() {
        const counter = ref(0);
        const user = ref({});

        const increment = () => {
            counter.value++;
        };

        const counterPorDos = computed(() => {
            return counter.value * 2;
        });

        fetch("https://jsonplaceholder.typicode.com/todos/1")
            .then((response) => response.json())
            .then((data) => {
                user.value = data;
            });

        return {
            counterPorDos,
            counter,
            user,
            increment,
        };
    },
};
</script> -->
