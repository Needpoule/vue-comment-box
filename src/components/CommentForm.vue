<template>
    <h2>Add your comment</h2>
    <form class="comment-form" v-on:submit.prevent="onSubmit">
        <label for="author">Author</label>
        <input id="author" type="text" placeholder="Your name" v-model="author" />
        <br />
        <label for="text">Comment</label>
        <input id="text" type="text" placeholder="Your comment" v-model="text" />
        <br />
        <input type="submit" value="Send" />
    </form>
</template>

<script>
    export default {
        data() {
            return {
                author: "",
                text: ""
            }
        },

        methods: {
            // Handle form submit
            onSubmit() {
                if (this.author != "" && this.text != "") {

                    // Dispatch event to parent components
                    this.$dispatch("new-comment", {
                        author: this.author,
                        text: this.text
                    });

                    // Reset Form
                    this.author = "";
                    this.text = "";
                }
            }
        }
    };
</script>

<style>
    .comment-form {
        margin-top: 10px;
        padding: 10px;
        border-top: 1px solid #eee;
    }
</style>
