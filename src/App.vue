<template>
  <div id="app">
        <ModalVue v-show="modalStatus"/>
        <router-view></router-view>
        <NotificationVue v-if="notificationStatus"/>
        <ConfirmationMsgVue v-if="getConfirmationMsgStatus"/>
  </div>
</template>

<script>
import PostsView from './views/PostsView.vue';
import {mapGetters, mapActions} from "vuex";
import './style.css'
import ConfirmationMsgVue from './components/notifications/confirmationMsg.vue';
import NotificationVue from './components/notifications/notification.vue';
import ModalVue from './components/Modal.vue';


export default {
  computed: {
    ...mapGetters(['getConfirmationMsgStatus', "notificationStatus", "notificationMsg", "modalStatus"])
  },
  methods: {
    ...mapActions(["getPosts", "getAuthors"])
  },

created() {
     this.getPosts()
     this.getAuthors()

  },
  components: {
    PostsView,
    ConfirmationMsgVue,
    NotificationVue,
    ModalVue,
  },
  
  
};
</script>

<style scoped>
#app {
  display: flex;
  box-sizing: border-box;
  justify-content: center;
  align-items: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  position: relative;
  width: 100%;
  min-height: 100%;
  max-height: fit-content;
  background-color: whitesmoke;
}
.success, .failure {
  position: absolute;
  top: 1rem;
  width: fit-content;
  height: fit-content;
  padding: 1rem;
  border-radius: 1rem;
}

</style>
