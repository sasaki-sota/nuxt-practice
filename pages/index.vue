<template>
  <div class="h-screen w-full flex items-center justify-center bg-blue-300 font-sans">
    <div class="bg-white rounded shadow p-6 m-4 w-full lg:w-3/4 lg:max-w-5xl">
      <div class="mb-4">
        <h1 class="text-red-300 text-5xl font-bold">Todoリスト</h1>
        <!--submit イベントによってページがリロードされない-->
        <form @submit.prevent="addTask()" class="mt-5">
          <span class="font-bold text-2xl">タスクを追加する</span>
          <input
            class="mt-3 shadow appearance-none border
             rounded w-full py-2 px-3 mr-4 text-grey-darker"
            placeholder="ここへ記述"
            v-model="task"
            type="text"
          >
        </form>
      </div>

      <div>
        <div
          v-for="(task, index) in tasks"
          :key="task.id"
          class="flex items-center mb-4">
          <p class="w-2/3 text-grey-darkest" :class="{done: task.isDone}">
            {{ task.name }}
          </p>
          <button v-if="task.isDone"
                  class="cursor-pointer mr-10"
                  @click="task.isDone = !task.isDone">
            <span class="text-green-500">解決済み</span>
          </button>
          <p v-else
             class="cursor-pointer"
             @click="task.isDone = !task.isDone">
            <span class="text-red-500">まだ未解決</span>
          </p>
          <p class="cursor-pointer"
             @click="removeTask(index)">
            <span class="text-blue-500">削除する</span>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">

import { defineComponent, reactive, toRefs } from "@nuxtjs/composition-api";

interface Task {
  name: string
  isDone: boolean
}


export default defineComponent({
  setup() {
    const state = reactive({
      task: "",
      tasks: [] as Task[]
    });

    const addTask = () => {
      const taskObj: Task = { name: state.task, isDone: false };
      state.tasks.push(taskObj);
      state.task = "";
    };

    const removeTask = (index: number) => {
      state.tasks.splice(index, 1);
    };

    return {
      ...toRefs(state),
      addTask,
      removeTask
    };
  }
});

</script>
