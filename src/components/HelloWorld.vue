<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<template>
  <div>
    <main class="pt-3">
      <div class="container-fluid" style="height: 2.5rem; display: flex; justify-content: flex-end;">
        <svg style="width: 28px; color: black; align-items: flex-end;" aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
          <path
            d="M10 0a10 10 0 1 0 10 10A10.011 10.011 0 0 0 10 0Zm0 5a3 3 0 1 1 0 6 3 3 0 0 1 0-6Zm0 13a8.949 8.949 0 0 1-4.951-1.488A3.987 3.987 0 0 1 9 13h2a3.987 3.987 0 0 1 3.951 3.512A8.949 8.949 0 0 1 10 18Z" />
        </svg>
      </div>

      <div class="container-fluid">
        <div class="row">
          <div class="col-md-12">
            <h4>Shortcuts</h4>
          </div>
        </div>

        <div class="row">
          <div class="col-md-12 col-12 mb-3">
            <div class="card  h-100">
              <div class="card-body" style="height: 30px;">

              </div>

            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-md-2 col-4 mb-3">
            <div class="card  h-100">
              <div class="card-body" style="height: 30px;">

              </div>

            </div>
          </div>
          <div class="col-md-2 col-4  mb-3">
            <div class="card  text-dark h-100">
              <div class="card-body" style="height: 30px;">

              </div>
            </div>
          </div>
          <div class="col-md-2 col-4 mb-3">
            <div class="card  h-100">
              <div class="card-body" style="height: 30px;">

              </div>
            </div>
          </div>
          <div class="col-md-2 col-4 mb-3">
            <div class="card  h-100">
              <div class="card-body" style="height: 30px;">

              </div>

            </div>
          </div>
          <div class="col-md-2 col-4 mb-3">
            <div class="card  h-100">
              <div class="card-body" style="height: 30px;">

              </div>

            </div>
          </div>
          <div class="col-md-2 col-4 mb-3">
            <div class="card  h-100">
              <div class="card-body" style="height: 30px;">

              </div>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <h4>Dashboard</h4>
          </div>
        </div>
        <div class="row px-2 m-2 mb-3" style="box-shadow: rgba(58, 53, 65, 0.1) 0px 2px 10px 0px;">
          <div class="col-md-3 mb-3">
            <div class="card  h-100"
              style="box-shadow: rgba(0, 0, 0, 0.1) 0px 10px 15px -3px, rgba(0, 0, 0, 0.05) 0px 4px 6px -2px; background-color: #16B1FF;">
              <h3 class="card-body "> 1</h3>

            </div>
          </div>
          <div class="col-md-3 mb-3">
            <div class="card  text-dark h-100"
              style="box-shadow: rgba(0, 0, 0, 0.1) 0px 10px 15px -3px, rgba(0, 0, 0, 0.05) 0px 4px 6px -2px;background-color: #9155FD;">
              <h3 class="card-body">34%</h3>
            </div>
          </div>
          <div class="col-md-3 mb-3">
            <div class="card  h-100"
              style="box-shadow: rgba(0, 0, 0, 0.1) 0px 10px 15px -3px, rgba(0, 0, 0, 0.05) 0px 4px 6px -2px; background-color: #56CA00;">
              <h3 class="card-body ">25K +</h3>

            </div>
          </div>
          <div class="col-md-3 mb-3">
            <div class="card  h-100"
              style="box-shadow: rgba(0, 0, 0, 0.1) 0px 10px 15px -3px, rgba(0, 0, 0, 0.05) 0px 4px 6px -2px; background-color: #FFB400;">
              <h3 class="card-body ">9k</h3>

            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-md-6 mb-3">
            <div class="card h-100">
              <div class="card-header" style="display: flex; justify-content: space-between; background-color: white;">

                Half width Card-1
                <svg style="z-index: 11;width: 5px; color: black" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                  fill="currentColor" viewBox="0 0 4 15">
                  <path
                    d="M3.5 1.5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 6.041a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 5.959a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Z" />
                </svg>
              </div>
              <div class="card-body">

              </div>
            </div>
          </div>
          <div class="col-md-6 mb-3">
            <div class="card h-100">
              <div class="card-header" style="display: flex; justify-content: space-between;  background-color: white;">

                Half width Card-2
                <svg style="z-index: 11;width: 5px; color: black" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                  fill="currentColor" viewBox="0 0 4 15">
                  <path
                    d="M3.5 1.5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 6.041a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 5.959a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Z" />
                </svg>
              </div>
              <div class="card-body">

              </div>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12 mb-3">
            <div class="card" style="height: 600px; ">
              <div class="card-header" style="display: flex; justify-content: space-between; background-color: white;">
                Full Width Card
                <svg style="z-index: 11;width: 5px; color: black" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                  fill="currentColor" viewBox="0 0 4 15">
                  <path
                    d="M3.5 1.5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 6.041a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 5.959a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Z" />
                </svg>
              </div>
              <div class="card-body">
                <div class="table-responsive" style="height: 400px;">

                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
