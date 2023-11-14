<template>
    <div>{{ tags }}</div>
    <!-- v directives -->
    <div v-text="tags.length"></div>
    <div v-if="!tags.length">
        You have no any tags. Enter it in the input
    </div>
    <div v-for="(tag, index) in tags">
        {{ tag }}
        <a @click.prevent="removeTag(index)" href="#">&times;</a>
    </div>
    
    <hr/>
    {{ newTag }}

    <input 
        type="text" 
        v-model.trim="newTag"
        @keydown.enter="addNewTag"
        @keydown.delete="removeLastTag"
        @keydown.tab.prevent="addNewTag"
    />
</template>

<script>
export default {
    data: () => ({
        tags: ["vue", "react", "angular"],
        newTag: "preact"
        // tags: []
    }),
    methods: {
        addNewTag(){
            if (this.newTag) {
                this.tags.push(this.newTag)
                this.newTag=""
            }
        },
        removeTag(index){
            this.tags.splice(index, 1)
        },
        removeLastTag(){
            if (this.newTag.length === 0) {
                this.removeTag(this.tags.length-1)
            }
        }
    },
}
</script>
