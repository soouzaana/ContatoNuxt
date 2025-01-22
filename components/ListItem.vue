<template>
  <div class="w-full p-4 border b-gray-200 flex items-center justify-between">
      <span class="text-xl font-semibold">
        <slot/>
      </span>

      <!-- Botões de ação -->
      <div class="w-32 space-x-7">
        <slot name="actions"/>
      </div>
    </div>
</template>