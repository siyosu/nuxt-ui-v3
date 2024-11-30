<template>
  <UContainer class="flex h-dvh">
    <UCard class="m-auto w-full max-w-sm">
      <template #header>
        <h1 class="text-xl font-bold">Login</h1>
      </template>

      <UForm :state="state" class="space-y-4" @submit="onSubmit">
        <UFormField label="Email" name="email">
          <UInput class="w-full" v-model.trim="state.email" />
        </UFormField>

        <UButton type="submit" label="Log in" block />
      </UForm>

      <template #footer>
        <p class="text-sm text-[var(--ui-text-muted)]">
          Don't have an account? <span class="text-[var(--ui-primary)] font-semibold">Sign up</span>
        </p>
      </template>
    </UCard>
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
