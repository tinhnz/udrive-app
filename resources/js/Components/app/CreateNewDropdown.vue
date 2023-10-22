<template>
    <Menu as="div" class="relative block text-left">
        <MenuButton
            class="inline-flex w-full justify-center rounded-md bg-black bg-opacity-20 px-4 py-2 text-sm font-medium text-white hover:bg-opacity-30 focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75"
        >
            Create New
            <PlusIcon
                class="ml-2 -mr-1 h-5 w-5 text-violet-200 hover:text-violet-100"
                aria-hidden="true"
            />
        </MenuButton>

        <transition
            enter-active-class="transition duration-100 ease-out"
            enter-from-class="transform scale-95 opacity-0"
            enter-to-class="transform scale-100 opacity-100"
            leave-active-class="transition duration-75 ease-in"
            leave-from-class="transform scale-100 opacity-100"
            leave-to-class="transform scale-95 opacity-0"
        >
            <MenuItems
                class="absolute left-0 mt-2 w-56 origin-top-right divide-y divide-gray-100 rounded-md bg-white shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none"
            >
                <div class="px-1 py-1">
                    <MenuItem v-slot="{ active }">
                        <a href="#" @click.prevent="showCreateFolderModal" class="block px-4 py-2 text-sm"> New Folder </a>
                    </MenuItem>
                </div>
                <div class="px-1 py-1">
                    <MenuItem v-slot="{ active }">
                        <a class="block px-4 py-2 text-sm"> Upload Files </a>
                    </MenuItem>
                    <MenuItem v-slot="{ active }">
                        <a class="block px-4 py-2 text-sm"> Upload Folders </a>
                    </MenuItem>
                </div>
            </MenuItems>
        </transition>
    </Menu>
    <CreateFolderModal v-model="createFolderModal"/>
</template>

<script setup>
import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";
import { PlusIcon } from "@heroicons/vue/20/solid";
import { ref } from "vue";
import CreateFolderModal from "@/Components/app/CreateFolderModal.vue"

const createFolderModal = ref(false)

function showCreateFolderModal() {
    createFolderModal.value = true
}
</script>

<style lang="scss" scoped></style>
