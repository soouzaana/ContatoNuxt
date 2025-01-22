<template>
  <div>
    <!-- Listagem dos contatos -->
    <div class="w-full px-2">
    <ListItem>
      Ana Maria

      <template #actions>
        <button>Editar</button>
        <button>Excluir</button>
      </template>
    </ListItem>
    </div>
    <UIButton
    @click="addContact"
    >ADICIONAR</UIButton>
  </div>
</template>

<script setup>
const router = useRouter();
const addContact = () => {
  router.push('/form');
};
</script>