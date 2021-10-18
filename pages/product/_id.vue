<template>
  <div>
    <h2>{{ product.name }}</h2>
    <img
      :src="
        product.imageUrl
          ? product.imageUrl
          : 'https://placeimg.com/200/200/tech'
      "
      width="200"
      style="float: right"
    />
    <h3>{{ product.description }}</h3>
    <p>Price: {{ product.price }}</p>
    <p>Fixed price? {{ product.fixedPrice }}</p>
    <p>Discontinued? {{ product.discontinued }}</p>
    <p>Modified date: {{ product.modifiedDate }}</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: this.product.name,
    };
  },
  asyncData(context) {
    const id = context.params.id;
    return context.$axios
      .get('https://storerestservice.azurewebsites.net/api/products/' + id)
      .then((res) => {
        return {
          product: res.data,
        };
      });
  },
};
</script>

<style lang="scss" scoped></style>
