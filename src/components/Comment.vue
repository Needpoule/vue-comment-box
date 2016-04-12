<template>
  <li class="comment">
      <span class="comment_author">{{ author }}</span>
      <span class="comment_text">{{ text }}</span>
  </li>
</template>

<script>
    export default {
        props: ["author", "text"]
    };
</script>

<style>
    .comment {
        list-style: none;
        height: 25px;
        line-height: 25px;
    }

    .comment .comment_author {
        font-weight: bold;
    }

    .comment .comment_text {
        font-style: italic;
        color: #333;
    }
</style>
