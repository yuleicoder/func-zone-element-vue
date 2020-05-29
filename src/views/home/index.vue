<template>
  <div class="desktop">
    <ul>
      <li class="add"><img src="../../assets/home/add.jpg" alt="#" @click="add"><span>应用管理</span></li>
      <div v-for="item in list">
        <li><img src="../../assets/home/app/tiger.jpg" alt="#" @click="imgClick"><span>{{ item.resourceName }}</span></li>
      </div>
    </ul>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Home',
  data() {
    return {
      list: [{id: 1, resourceName: '用户管理'}, {id: 2, resourceName: '人像比对'}],
      num: 2
    }
  },
  computed: {
    ...mapGetters([
      'name'
    ])
  },
  methods: {
    imgClick: function() {
      this.$router.push('/views/user/index')
    },
    add() {
      this.list.push({id: this.num++, resourceName: '资源APP'})
      // getUserInfo({id: '', username: '', password: ''}).then(res => {
      //   this.list.push(this.num);
      //   this.num++;
      // }).catch(err => {
      //   console.log('<----------------err------------->', err);
      // });
    },
    logout() { // 退出登录
      this.$confirm('确认退出吗?', '', {
        type: 'warning'
      })
        .then(() => {
          this.$router.push('/')
        })
        .catch(() => {
        })
    }
  }
}
</script>

<style lang="scss" scoped>
  @import './index.css';
</style>
