<template>
  <div class="comment-box">
    <h1>Comments</h1>
    <comment-list :comments="comments"></comment-list>
    <comment-form></comment-form>
  </div>
</template>

<script>
    import CommentList from "./CommentList.vue";
    import CommentForm from "./CommentForm.vue";

    export default {
        components: { CommentList, CommentForm },
        data () {
            return {
                comments: [
                    {author: "Mike", text: "This is a comment"},
                    {author: "Joe", text: "This is another comment"},
                ]
            }
        },

        events: {
            // Add new comment
            "new-comment": function(comment) {
                this.comments.push(comment);
            }
        }
    }
</script>

<style>
    .comment-box {
        width: 300px;
        margin: 0 auto;
    }
</style>
