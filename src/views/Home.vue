<template>
  <div>
    <el-container>
      <el-header>Header</el-header>
      <el-container>
        <el-aside class="side-menu">
              <el-menu
                      default-active="2"
                      class=""
                      @open="handleOpen"
                      @close="handleClose"
                      background-color="#545c64"
                      text-color="#fff"
                      active-text-color="#ffd04b">
                <templete v-for="item of items">
                  <el-submenu :index="item.index" :key="item.index">
                    <template slot="title">
                      <i class="el-icon-location"></i>
                      <span>{{item.title}}</span>
                    </template>
                    <templete v-if="item.subs">
                      <el-menu-item-group v-for="subsItem of item.subs">
                        <template slot="title">分组一</template>
                        <el-menu-item index="1-1">选项1</el-menu-item>
                        <el-menu-item index="1-2">选项2</el-menu-item>
                      </el-menu-item-group>
                    </templete>

                    <el-menu-item-group title="分组2">
                      <el-menu-item index="1-3">选项3</el-menu-item>
                    </el-menu-item-group>
                    <el-submenu index="1-4">
                      <template slot="title">选项4</template>
                      <el-menu-item index="1-4-1">选项1</el-menu-item>
                    </el-submenu>
                  </el-submenu>
                  <el-menu-item index="2">
                    <i class="el-icon-menu"></i>
                    <span slot="title">导航二</span>
                  </el-menu-item>
                  <el-menu-item index="3" disabled>
                    <i class="el-icon-document"></i>
                    <span slot="title">导航三</span>
                  </el-menu-item>
                  <el-menu-item index="4">
                    <i class="el-icon-setting"></i>
                    <span slot="title">导航四</span>
                  </el-menu-item>
                </templete>

              </el-menu>
        </el-aside>
        <el-main>Main</el-main>
      </el-container>

    </el-container>
  </div>

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  data () {
    return {
      items: [
        {
          icon: 'el-icon-lx-home',
          index: 'dashboard',
          title: '问答状态'
        },
        {
          icon: 'el-icon-lx-cascades',
          index: '7',
          title: '知识管理',
          subs: [
            {
              index: 'topquestion',
              title: 'top问题'
            },
            {
              index: 'nomark',
              title: '未标注'
            },
            {
              index: 'notdispose',
              title: '暂不处理'
            },
            {
              index: 'notentertained',
              title: '不予处理'
            },
            {
              index: 'marked',
              title: '已标注'
            },
            {
              index: 'matching',
              title: '匹配门限'
            },
            {
              index: 'upwarehouse',
              title: '入库'
            }
          ]
        },
        {
          icon: 'el-icon-lx-edit',
          index: '8',
          title: '知识库维护',
          subs: [
            {
              index: 'knowledgeEdit',
              title: '编辑'
            },
            {
              index: 'knowledgeImportExport',
              title: '导入导出'
            },
            {
              index: 'knowledgeCorpus',
              title: '语料导入'
            },
            {
              index: 'knowledgeOperateHistory',
              title: '操作历史'
            }
          ]
        },
        {
          icon: 'el-icon-lx-settings',
          index: '9',
          title: '用户管理',
          subs: [
            {
              index: 'setting',
              title: '用户管理'
            },
          ]
        }
      ]
    }
  },
  components: {
    HelloWorld
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
}
</script>
<style scoped>
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }

  .el-aside {
    background-color: #545c64;
    color: #333;
    text-align: center;
    line-height: 200px;
  }

  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }

  body > .el-container {
    margin-bottom: 40px;
  }
  .side-menu {
    position: absolute;
    bottom: 5px;
    top: 70px;

  }
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }

  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
