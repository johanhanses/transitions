<script setup lang="ts">
const show1 = ref(false)
const show2 = ref(false)
const show3 = ref(false)

const loading = ref(false)

const handleLogin = () => {
  loading.value = true
  // fake an API call being resolved.
  setTimeout(() => {
    loading.value = false
  }, 1500)
}
</script>

<template>
  <div class="bg-gray-900 min-h-screen">
    <header class="bg-gray-900 text-white leading-normal font-karla z-10 shadow-lg">
      <nav>
        <ul class="flex justify-center py-2">
          <li class="relative flex justify-center p-3" @mouseenter="show1 = true" @mouseleave="show1 = false">
            <MenuGroup :show="show1" width="w-[200px]">
              <template #default>
                Item
              </template>
              <template #menuItem>
                <MenuItem>
                  <One /> <span class>Lorem, ipsum dolor.</span>
                </MenuItem>
                <MenuItem>
                  <One /> <span class>Lorem, ipsum dolor.</span>
                </MenuItem>
                <MenuItem>
                  <One /> <span class>Lorem, ipsum dolor.</span>
                </MenuItem>
              </template>
            </MenuGroup>
          </li>
          <li class="relative flex justify-center p-3" @mouseenter="show2 = true" @mouseleave="show2 = false">
            <MenuGroup :show="show2" width="w-[285px]">
              <template #default>
                Item 2
              </template>
              <template #menuItem>
                <MenuItem>
                  <One /> <span class>Lorem ipsum dolor sit amet, con.</span>
                </MenuItem>
                <MenuItem>
                  <One /> <span class>Lorem ipsum dolor sit amet, con.</span>
                </MenuItem>
              </template>
            </MenuGroup>
          </li>
          <li class="relative flex justify-center p-3" @mouseenter="show3 = true" @mouseleave="show3 = false">
            <MenuGroup :show="show3" width="w-[252px]">
              <template #default>
                Item 3
              </template>
              <template #menuItem>
                <MenuItem>
                  <One /> <span class>Lorem, ipsum dolor sit am.</span>
                </MenuItem>
                <MenuItem>
                  <One /> <span class>Lorem, ipsum dolor sit am.</span>
                </MenuItem>
                <MenuItem>
                  <One /> <span class>Lorem, ipsum dolor sit am.</span>
                </MenuItem>
                <MenuItem>
                  <One /> <span class>Lorem, ipsum dolor sit am.</span>
                </MenuItem>
              </template>
            </MenuGroup>
          </li>
        </ul>
      </nav>
      <Button :loading="loading" class="absolute top-5 right-6" @click="handleLogin">
        <SpinnerIcon v-if="loading" />
        <template v-else>
          <UserIcon /><span>Login</span>
        </template>
      </Button>
    </header>
  </div>
</template>
