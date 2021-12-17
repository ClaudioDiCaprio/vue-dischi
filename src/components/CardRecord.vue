<template>
    <div class="record">
        <img :src="elements.poster" :alt="elements.title">
        <h3>{{elements.title.toUpperCase()}}</h3>
        <span>{{elements.author}}</span>
        <span>{{elements.year}}</span>
    </div>
</template>

<script>
export default {
  name: 'CardRecord',
  props: { 
      elements: Object,
  }
}
</script>

<style scoped lang="scss">
    .record {
        width: calc(20% - 40px);
        background-color: #2e3a46;
        margin: 0 20px 30px;
        padding: 20px;
        text-align: center;
        transition: all .1s ease;
        cursor: pointer;
        img {
            width: 100%;
            margin-bottom: 20px;
        }
        h3 {
            margin-bottom: 20px;
            color: white;
            font-size: 1rem;
        }
        span {
            display: block;
            color: #777d7a;
            font-size: .9rem;
        }
        &:hover {
            transform: scale(1.03);
        }
    }
</style>