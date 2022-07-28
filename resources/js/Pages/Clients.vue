<script setup>
import BreezeAuthenticatedLayout from "@/Layouts/Authenticated.vue";
import { Head } from "@inertiajs/inertia-vue3";

defineProps(['clients', 'token']);

</script>

<template>
  <Head title="Client" />

  <BreezeAuthenticatedLayout>
    <template #header>
      <h2 class="font-semibold text-xl text-gray-800 leading-tight">Client</h2>
    </template>

    <div class="py-12">
      <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
        <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
          <div class="p-6 bg-white border-b border-gray-200">
            <p>List of client</p>

            <div class="py-3 text-gray-500" v-for="client in this.clients" :key="client.id">
              <h3 class="text-lg text-gray-500">{{ client.name }}</h3>
              <p><b>ID</b> {{ client.id }}</p>
              <p><b>Redirect</b> {{ client.redirect }}</p>
            </div>
          </div>

          <div class="mt-3 p-6 bg-white border-b border-gray-200">
            <form action="/oauth/clients" method="POST">
              <div>
                <label for="name">Name</label>
                <input
                  type="text"
                  name="name"
                  placeholder="Client Name"
                />
              </div>
              <div class="mt-2">
                <label for="redirect">Redirect</label>
                <input
                  type="text"
                  name="redirect"
                  placeholder="https://my-url.com/callback"
                />
              </div>
              <div class="mt-3">
                 <input type="hidden" name="_token" :value="this.token" />
                <button type="submit">Create Client</button>
              </div>
            </form>
          </div>
          <!-- end div form -->
        </div>
      </div>
    </div>
  </BreezeAuthenticatedLayout>
</template>
