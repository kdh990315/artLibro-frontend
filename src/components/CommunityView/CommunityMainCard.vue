<script setup lang="ts">
defineProps<{
  post: {
    title: string
    image: string
    date: string
    author: string
    comment: number
    likes: number
  }
}>()
</script>

<template>
  <div class="post-card">
    <div class="post-info">
      <h3 class="post-title">{{ post.title }}</h3>
      <p class="post-date">{{ post.date }}</p>
      <div class="divider"></div>
      <div class="post-meta">
        <p>
          작성자 <span>{{ post.author }}</span>
        </p>
        <p>
          댓글수 <span>{{ post.comment }}</span>
        </p>
        <p>
          좋아요 <span>{{ post.likes }}</span>
        </p>
      </div>
    </div>
    <img :src="post.image" alt="책표지" class="post-image" />
    <div class="new-post-badge">최신</div>
  </div>
</template>

<style lang="scss" scoped>
.post-card {
  width: 416px;
  height: 217px;
  background: $secondary-color-300;
  color: white;
  padding: 30px;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 0px;

  .post-info {
    display: flex;
    flex-direction: column;
    margin-bottom: 0;
  }

  .post-title {
    font-size: 24px;
    margin-top: 0px;
    margin-bottom: 20px;
  }

  .post-date {
    font-size: 16px;
  }

  .divider {
    width: 100%;
    height: 1px;
    background: white;
  }

  .post-meta {
    font-size: 14px;
    display: flex;
    flex-direction: column;
    margin-top: 10px;

    p {
      display: flex;
      align-items: center;
      gap: 10px;

      margin-bottom: 0;
    }
  }

  .post-image {
    width: 110px;
    height: 150px;
    position: absolute;
    bottom: 50px;
    right: 15px;
    border-radius: 5px;
  }

  .new-post-badge {
    width: 45px;
    height: 23px;
    position: absolute;
    top: 0;
    right: 0;
    background: black;
    color: white;
    font-size: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
