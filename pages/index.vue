<template>
  <UContainer class="flex h-dvh">
    <div class="m-auto w-full max-w-sm">
      <UForm :state="state" class="space-y-4" @submit="onSubmit">
        <h1 class="text-xl font-bold">Login</h1>
        <UFormField label="Email" name="email">
          <UInput class="w-full" v-model.trim="state.email" />
        </UFormField>

        <UButton type="submit" label="Log in" block />
      </UForm>
    </div>
  </UContainer>
</template>

<script setup lang="ts">
const state = reactive({
  email: "",
});

const toast = useToast();
async function onSubmit() {
  toast.add({
    title: "Login success",
    description: `User: ${state.email}`,
  });
}
</script>
