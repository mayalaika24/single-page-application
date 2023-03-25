<template>
  <div class="text-center">
    <v-dialog
        v-model="dialog"
        width="50%"
        persistent
    >
      <v-card>
        <v-card-text>
          <div class="welcoming">
            Cause your are important to us thank you for sharing your opinion <img class="heart" src="../../assets/red-heart-icon.svg"/>
          </div>
        </v-card-text>
      </v-card>
    </v-dialog>
  </div>
</template>
<script>
export default {
  data () {
    return {
      dialog: true,
    }
  },
}
</script>
<style>
.welcoming{
  font-size: 25px;
  padding-top: 20px;
}
img.heart{
  width: 25px;
  height: 25px;
}
</style>
