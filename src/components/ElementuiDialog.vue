<template>
  <div>
    <el-button type="text" @click="dialogVisible = true">点击打开 Dialog</el-button>

    <el-dialog
      v-drag
      title="提示"
      :visible.sync="dialogVisible"
      :modal="false"
      :close-on-click-modal="false"
      width="30%">
      <span>这是一段信息</span>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  }
})
export default class App extends Vue {
  private dialogVisible = false

  private handleClose(done: any) {
    this.$confirm('确认关闭？')
    .then(_ => {
      done();
    })
    .catch(_ => {});
  }
}
</script>
