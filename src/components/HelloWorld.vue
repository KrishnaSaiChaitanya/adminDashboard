<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<template>
  <div class="d-flex">
    <div class=" sidebar-nav bg-dark" id="sidebar" style="width: 25%;">
    </div>
    <main class="mt-5 pt-3" style="width: 100%;">
      <div class="container-fluid">
        <div class="row">
          <div class="col-md-12">
            <h4>Dashboard</h4>
          </div>
        </div>
        <div class="row">
          <div class="col-md-3 mb-3">
            <div class="card  h-100">
              <div class="card-body py-5" style="box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;"> Card 1</div>

            </div>
          </div>
          <div class="col-md-3 mb-3">
            <div class="card  text-dark h-100">
              <div class="card-body py-5">Card 2</div>

            </div>
          </div>
          <div class="col-md-3 mb-3">
            <div class="card   h-100">
              <div class="card-body py-5">Card 3</div>

            </div>
          </div>
          <div class="col-md-3 mb-3">
            <div class="card  h-100">
              <div class="card-body py-5">Card 4</div>

            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-md-6 mb-3">
            <div class="card h-100">
              <div class="card-header">
                <span class="me-2"><i class="bi bi-bar-chart-fill"></i></span>
                Half width Card-1
              </div>
              <div class="card-body">
                <canvas class="chart" width="400" height="200"></canvas>
              </div>
            </div>
          </div>
          <div class="col-md-6 mb-3">
            <div class="card h-100">
              <div class="card-header">
                <span class="me-2"><i class="bi bi-bar-chart-fill"></i></span>
                Half Width Card-2
              </div>
              <div class="card-body">
                <canvas class="chart" width="400" height="200"></canvas>
              </div>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12 mb-3">
            <div class="card">
              <div class="card-header">
                <span><i class="bi bi-table me-2"></i></span> Full Width Card
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
