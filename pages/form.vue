<template>
  <div><form>
    <UIInput label="Nome" type="text" v-model="contact.name" />
    <UIInput label="E-mail" type="email" v-model="contact.email" />
    <UIInput label="Telefone" type="text" v-model="contact.phone" />
    <UIButton type="submit" @click="saveContact">SALVAR</UIButton></form>
  </div>
</template>

<script setup>
const { createContact, getContact, updateContact } = useContacts();
const router = useRouter();
const route = useRoute();

const contact = reactive({
  id: "",
  name: "",
  email: "",
  phone: "",
});

onMounted(() => {
  const id = route.query.id;

  if (id) {
    const { name, email, phone } = getContact(id);

    contact.id = id;
    contact.name = name;
    contact.email = email;
    contact.phone = phone;
  }
});

const saveContact = () => {
  if (contact.id) {
    updateContact(contact.id, contact);
  } else {
    createContact(contact);
  }

  router.push("/");
}
</script>