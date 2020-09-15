<template>
  <ul class="wrapper">
    <li v-for="(item, index) in list" :key="'item'+index">
      <!-- font awesome icon with a rotating animation -->
      <i class="fas fa-chevron-circle-right"
         :class="{'open':item.open}"></i>
      <!-- The list title with the click event for toggling the open status -->   
      <div class="title" @click="item.open = !item.open">
        {{ item.title }}
      </div>
      <!-- renders the ListItem Component for each list element -->
      <ListItem :list="item" />
    </li>
  </ul>
</template>

<script>
  import ListItem from "./ListItem";

  export default {
    data: () => {
      return {
        /*
          Some test data for the accordion, 
          you can use this for a sidebar navigation or simply as a faq list, for example
        */
        list: [
          {
            title: "Projects",
            open: false,
            sublist: [
              "Vue.js", "SCSS", "JavaScript", "Webpack"
            ]
          },
          {
            title: "Portfolio",
            open: false,
            sublist: [ "Transitions", "Course A" ]
          },
          { 
            title: "Timeline", 
            open: false, 
            sublist: [ "2017", "2018", "2019" ] 
          },
          {
            title: "Resources",
            open: false,
            sublist: ["GitHub", "YouTube", "Dev.to"]
          },
          {
            title: "Documentation",
            open: false,
            sublist: ["Article A", "Article B"]
          }
        ]
      };
    },
    components: {
      ListItem
    }
  };
</script>

<style lang="scss" scoped>
  .wrapper {
    list-style: none;
    background-color: #fefefe;
    box-shadow: 0 2px rgba($color: #000000, $alpha: .15);
    border-radius: 4px;
    overflow: hidden;

    li {
      position: relative;
      color: #555;
      border-top: 1px solid #dedede;
      cursor: pointer;

      .title {
        padding: 10px 0;
        text-indent: 20px;
      }

      /*
        CSS definition for the icon
        If the open status from the clicked element equal to true, 
        then the open class is connected and the icon rotates
        90 deg to the bottom, otherwise back to the default position.
      */
      i {
        position: absolute;
        top: 14px;
        right: 10px;
        transition: transform .5s ease-in-out;

        &.open {
          transform: rotateZ(90deg);
        }
      }

      &:hover {
        color: #4f7351;
        background-color: #DFEEE0;
      }
    }
  }
</style>
