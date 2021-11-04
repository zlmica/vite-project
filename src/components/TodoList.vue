<script setup>
import { useTodos } from "../utils/todo";

let { title, todos, addTodo, clear, active, all, allDone } = useTodos();
</script>

<template>
  <div
    class="
      p-6
      max-w-sm
      mx-auto
      bg-white
      rounded-xl
      shadow-md
      flex
      items-center
      space-x-4
      mb-10
    "
  >
    <div class="flex-shrink-0">
      <div class="h-12 w-12 bg-yellow-200"></div>
    </div>
    <div>
      <div class="text-xl font-medium text-black">ChitChat</div>
      <p class="text-gray-500">You have a new message!</p>
    </div>
  </div>
  <div class="mb-10 py-8 px-8 max-w-sm mx-auto bg-white rounded-xl shadow-md space-y-2 sm:py-4 sm:flex sm:items-center sm:space-y-0 sm:space-x-6">
    <div class="block mx-auto w-24 h-24 rounded-full sm:mx-0 sm:flex-shrink-0 bg-red-600"></div>
    <div class="text-center space-y-2 sm:text-left">
      <div class="space-y-0.5">
        <p class="text-lg text-black font-semibold">
          Erin Lindford
        </p>
        <p class="text-gray-500 font-medium">
          Product Engineer
        </p>
      </div>
      <button class="px-4 py-1 text-sm text-purple-600 font-semibold rounded-full border border-purple-200 hover:text-white hover:bg-purple-600 hover:border-transparent focus:outline-none focus:ring-2 focus:ring-purple-600 focus:ring-offset-2">Message</button>
    </div>
  </div>

 <button class="py-2 px-4 font-semibold rounded-lg shadow-md text-white bg-green-500 hover:bg-green-700">
  Click me
</button>

  <div class="container mx-auto bg-yellow-200">
    <textarea class="resize-x" name="" id="" cols="30" rows="10"></textarea>
    <input
      class="border-blue-300 border ml-6 p-3 rounded-full"
      type="text"
      v-model="title"
      @keydown.enter="addTodo"
    />
    <button v-if="active < all" @click="clear">清理</button>
    <ul v-if="todos.length">
      <li v-for="(todo, index) in todos" :key="todo + index">
        <input type="checkbox" v-model="todo.done" />
        <span :class="{ done: todo.done }">{{ todo.title }}</span>
      </li>
    </ul>
    <div v-else>暂无数据</div>
    <div>
      全选<input type="checkbox" v-model="allDone" />
      <span>{{ active }} / {{ all }}</span>
    </div>
  </div>
</template>

<style scoped>
.done {
  text-decoration: line-through;
}
</style>
