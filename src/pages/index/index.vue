<template>
  <view class="demo">
    <view> 欢迎使用 NutUI 开发 Taro 多端项目 <Dongdong /> </view>
    <view>{{ count }}</view>
    <view>
      <nut-button type="primary" @click="handleClick"> Count++ </nut-button>
    </view>

    <nut-elevator
      :index-list="data"
      :height="260"
      @click-item="clickItem"
      @click-index="clickIndex"
    />

    <nut-form>
      <nut-form-item label="姓名">
        <nut-input
          v-model="formData.name"
          placeholder="请输入姓名"
          type="text"
        />
      </nut-form-item>
      <nut-form-item label="年龄">
        <nut-input
          v-model="formData.age"
          placeholder="请输入年龄"
          type="text"
        />
      </nut-form-item>
      <nut-form-item label="联系电话">
        <nut-input
          v-model="formData.tel"
          placeholder="请输入联系电话"
          type="text"
        />
      </nut-form-item>
      <nut-form-item label="地址">
        <nut-input
          v-model="formData.addr"
          placeholder="请输入地址"
          type="text"
        />
      </nut-form-item>
      <nut-form-item label="备注">
        <nut-textarea
          v-model="formData.info"
          placeholder="请输入备注"
          type="text"
        />
      </nut-form-item>
    </nut-form>
  </view>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { Dongdong } from '@nutui/icons-vue-taro'

const count = ref(0)

const formData = ref({
  name: '',
  age: '',
  tel: '',
  addr: '',
  info: ''
})

const handleClick = () => {
  count.value++
}

const data = ref([
  {
    title: 'A',
    list: [{ name: '安徽', id: 1 }]
  },
  {
    title: 'B',
    list: [{ name: '北京', id: 2 }]
  },
  {
    title: 'G',
    list: [
      { name: '广西', id: 3 },
      { name: '广东', id: 4 }
    ]
  },
  {
    title: 'H',
    list: [
      { name: '湖南', id: 5 },
      { name: '湖北', id: 6 }
    ]
  }
])

const clickItem = (key: string, item: any) => {
  console.log(key, item)
}

const clickIndex = (key: string) => {
  console.log(key)
}
</script>

<style>
.demo {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
