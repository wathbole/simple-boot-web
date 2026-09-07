<template>
  <div>
    <el-card shadow="never">
      <div class="flex items-center">
        <el-avatar :src="avatar" :size="70" class="mr-16px">
          <img src="@/assets/imgs/avatar.gif" alt="" />
        </el-avatar>
        <div>
          <div class="text-20px">
            {{ t('workplace.welcome') }} {{ username }} {{ t('workplace.happyDay') }}
          </div>
          <div class="mt-10px text-14px text-gray-500">欢迎使用 Simple Boot 管理后台</div>
        </div>
      </div>
    </el-card>

    <el-card shadow="never" class="mt-8px">
      <template #header>
        <span>{{ t('workplace.shortcutOperation') }}</span>
      </template>
      <el-row>
        <el-col v-for="item in shortcut" :key="item.name" :span="8" class="mb-8px">
          <div class="flex items-center">
            <Icon :icon="item.icon" class="mr-8px" :style="{ color: item.color }" />
            <el-link type="default" :underline="false" @click="handleShortcutClick(item.url)">
              {{ item.name }}
            </el-link>
          </div>
        </el-col>
      </el-row>
    </el-card>
  </div>
</template>
<script lang="ts" setup>
import { useUserStore } from '@/store/modules/user'
import type { Shortcut } from './types'
import { useRouter } from 'vue-router'

defineOptions({ name: 'Index' })

const { t } = useI18n()
const router = useRouter()
const userStore = useUserStore()
const avatar = userStore.getUser.avatar
const username = userStore.getUser.nickname

const shortcut = reactive<Shortcut[]>([
  {
    name: '首页',
    icon: 'ion:home-outline',
    url: '/',
    color: '#1fdaca'
  },
  {
    name: '用户管理',
    icon: 'ep:user',
    url: '/system/user',
    color: '#409EFF'
  },
  {
    name: '角色管理',
    icon: 'ep:user-filled',
    url: '/system/role',
    color: '#67C23A'
  },
  {
    name: '菜单管理',
    icon: 'ep:menu',
    url: '/system/menu',
    color: '#E6A23C'
  },
  {
    name: '基础设施',
    icon: 'ep:monitor',
    url: '/infra/server',
    color: '#909399'
  }
])

const handleShortcutClick = (url: string) => {
  router.push(url)
}
</script>
