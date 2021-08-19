<template>
    <div></div>
</template>

<script>
export default {
    props: {
        Tasks : Array,
        
    },
    data: () => ({
        newTask: "",
        Tasks: ["Despertar"],
    }),
    methods: {
        erase() {
            this.Tasks.push(this.newTask)
            this.newTask = ""
        },
    },
}
</script>