<template>
    <div>{{ tags }}</div>
    <!-- v directives -->
    <div v-text="tags.length"></div>
    <div v-if="!tags.length">
        You have no any tags. Enter it in the input
    </div>
    <div v-for="(tag, index) in tags">{{ index + ":" + tag }}</div>
    
    <input 
        type="text" 
        :value="newTag" 
        @keydown.enter="tags.push($event.target.value)"
        @keydown.tab.prevent="tags.push($event.target.value)"
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
