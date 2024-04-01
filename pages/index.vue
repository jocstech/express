<!--
 * @Author       : Yulong(Joseph) Fang <aionv@qq.com>
 * @Date         : 2024-04-01 22:59:56
 * @LastEditors  : Yulong(Joseph) Fang <aionv@qq.com>
 * @LastEditTime : 2024-04-01 23:16:44
 * @Description  :
-->
<script setup lang="ts">
const online = useOnline()
</script>

<template>
  <div>
    <Logos mb-6 />
    <div>
      <h1>你好世界！</h1>
    </div>
    <Suspense>
      <ClientOnly>
        <PageView v-if="online" />
        <div v-else text-gray:80>
          You're offline
        </div>
      </ClientOnly>
      <template #fallback>
        <div italic op50>
          <span animate-pulse>Loading...</span>
        </div>
      </template>
    </Suspense>
    <InputEntry />
  </div>
</template>
