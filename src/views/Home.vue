<template>
  <div class="home">
    <div class="mt-10">
      <Button
        roomName="testing"
        email="fotiecodes@gmail.com"
        displayName="fotiecodes"
        color="primary"
        roundedBtnWithIcon
      />
    </div>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
// @ is an alias to /src

export default {
  name: "Home",
  components: { Button },
};
</script>
