<script setup>
    import { ref } from "vue";

    const list = ref([]);
    
    const newitem = ref("");
    
function additem() {
    list.value.push(newitem.value);
    newitem.value = "";
}

function deleteitem(index) {
    list.value.splice(index, 1);
}

</script>



<!-- create a todolist with vue where i can delete items -->

<template>
    <div>
        <input type="text" v-model="newitem" />
        <button @click="additem">Add Item</button>
        <ul>
            <li v-for="item in list" :key="item">
                {{ item }}
                <button @click="deleteitem(item)">Delete</button>
            </li>
        </ul>
    </div>
</template>




