<script setup lang="ts">
import {ref} from "vue"
import Login from "~/utils/server/user/login";

const router = useRouter()
const usernameRef = ref("")
const passwordRef = ref("")
const onSubmit = (e: Event) => {
  e.preventDefault()
  Login(usernameRef.value, passwordRef.value)
  router.push('/')
}
</script>

<template>
  <div class="hero min-h-screen bg-base-200">
    <div class="hero-content flex-col ">
      <div class="text-center lg:text-left">
        <h1 class="text-5xl font-bold mb-4">stockOverflow</h1>
      </div>
      <div class="card flex-shrink-0 w-full max-w-sm shadow-2xl bg-base-100">
        <div class="m-8 mt-4 mb-2">
          <div class="form-control">
            <label class="label">
              <span class="label-text">Email</span>
            </label>
            <input
              v-model="usernameRef"
              placeholder="username"
              class="input input-bordered"
            />
          </div>
          <div class="form-control">
            <label class="label">
              <span class="label-text">Password</span>
            </label>
            <input
              v-model="passwordRef"
              type="password"
              placeholder="password"
              class="input input-bordered"
            />
          </div>
          <div class="form-control mt-2">
            <button @click="onSubmit" class="btn btn-primary m-6">Login</button>
          </div>
        </div>
      </div>
      <div class="flex gap-10">
        <label class="">
          <a href="/signup" class="label-text-alt link link-hover"
            >Create Account</a
          >
        </label>
      </div>
    </div>
  </div>
</template>
