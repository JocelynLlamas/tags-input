<template>
    <div>{{ tags }}</div>
    <!-- v directives -->
    <div v-text="tags.length"></div>
    <div v-if="!tags.length">
        You have no any tags. Enter it in the input
    </div>
    <div v-for="(tag, index) in tags">{{ tag }}</div>
    
    <hr/>
    {{ newTag }}

    <input 
        type="text" 
        v-model.trim="newTag"
        @keydown.enter="tags.push(newTag)"
        @keydown.tab.prevent="tags.push(newTag)"
    />
</template>

<script>
export default {
    data: () => ({
        tags: ["vue", "react", "angular"],
        newTag: "preact"
        // tags: []
    }) 
}
</script>
