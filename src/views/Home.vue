<template>
  <div class="home">
    <div id="read"></div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Epub, { Book } from "epubjs";
@Component({
  components: {}
})
export default class Home extends Vue {
  book: Book;
  constructor(){
    super();
    this.book = Epub("/146678.epub");
  }
  mounted() {
    console.log(this.book.renderTo);
    this.book.renderTo("read", {
      width: window.innerWidth,
      height: window.innerHeight
    }).display();
  }
}
</script>
