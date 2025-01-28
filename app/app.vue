<template>
  <UContainer class="min-h-screen flex flex-col my-4">
    <div class="mb-2 text-right">
      <UButton
        square
        variant="ghost"
        color="black"
        :icon="
          $colorMode.preference === 'dark' || $colorMode.preference === 'system'
            ? 'i-heroicons-moon'
            : 'i-heroicons-sun'
        "
        @click="isDarkMode = !isDarkMode"
      />
    </div>

    <UCard>
      <template #header>
        <h3 class="text-lg font-semibold leading-6">
          <NuxtLink to="/">
            Atidone
          </NuxtLink>
        </h3>
        <UButton
          v-if="!loggedIn"
          to="/api/auth/github"
          icon="i-simple-icons-github"
          label="Login with GitHub"
          color="black"
          size="xs"
          external
        />
        <div
          v-else
          class="flex flex-wrap -mx-2 sm:mx-0"
        >
          <UButton
            to="/todos"
            icon="i-heroicons-list-bullet"
            label="Todos"
            :color="$route.path === '/todos' ? 'primary' : 'gray'"
            variant="ghost"
          />
          <UButton
            to="/optimistic-todos"
            icon="i-heroicons-sparkles"
            label="Optimistic Todos"
            :color="$route.path === '/optimistic-todos' ? 'primary' : 'gray'"
            variant="ghost"
          />
          <UButton
            to="/login"
            icon="i-heroicons-login"
            label="Login"
            :color="$route.path === '/login' ? 'primary' : 'gray'"
            variant="ghost"
          />
          <UButton
            to="/maintenance-request"
            icon="i-heroicons-maintenance"
            label="Maintenance Request"
            :color="$route.path === '/maintenance-request' ? 'primary' : 'gray'"
            variant="ghost"
          />
          <UButton
            to="/maintenance-status"
            icon="i-heroicons-maintenance"
            label="Maintenance Status"
            :color="$route.path === '/maintenance-status' ? 'primary' : 'gray'"
            variant="ghost"
          />
          <UButton
            to="/privacy"
            icon="i-heroicons-privacy"
            label="Privacy"
            :color="$route.path === '/privacy' ? 'primary' : 'gray'"
            variant="ghost"
          />
          <UButton
            to="/register"
            icon="i-heroicons-register"
            label="Register"
            :color="$route.path === '/register' ? 'primary' : 'gray'"
            variant="ghost"
          />
          <UButton
            to="/profile"
            icon="i-heroicons-profile"
            label="Profile"
            :color="$route.path === '/profile' ? 'primary' : 'gray'"
            variant="ghost"
          />
          <UButton
            to="/dashboard"
            icon="i-heroicons-dashboard"
            label="Dashboard"
            :color="$route.path === '/dashboard' ? 'primary' : 'gray'"
            variant="ghost"
          />
        </div>
      </template>
      <NuxtPage />
    </UCard>

    <footer class="text-center mt-2">
      <NuxtLink
        href="https://github.com/atinux/atidone"
        target="_blank"
        class="text-sm text-gray-500 hover:text-gray-700"
      >
        GitHub
      </NuxtLink>
      ·
      <NuxtLink
        href="https://twitter.com/atinux"
        target="_blank"
        class="text-sm text-gray-500 hover:text-gray-700"
      >
        Twitter
      </NuxtLink>
    </footer>
  </UContainer>
  <UNotifications />
</template>
