<template>
  <div>
    <div id="slogan" class="text-center">
      <h1 class="text-center">NameHelper</h1>
      <br/>
      <h6 class="text-secondary">Name's generator using Vue.js, Graphcl and Node.js</h6>
    </div>
    <div id="main">
      <div class="container">
        <div class="row">
          <div class="col-md">
            <h5>Prefixes <span class="badge bg-info">{{ prefixes.length }}</span> </h5>
            <div class="card">
              <div class="card-body">
                <ul class="list-group">
                  <li class="list-group-item" v-for="prefix in prefixes" :key="prefix">
                    {{ prefix }}
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <div class="col-md">
            <h5>Sufixes <span class="badge bg-info">{{ sufixes.length}}</span> </h5>
            <div class="card">
              <div class="card-body">
                <ul class="list-group">
                  <li class="list-group-item" v-for="sufix in sufixes" :key="sufix">
                    {{ sufix }}
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
        <br/>
        <h5>Domains <span class="badge bg-info">{{ domains.length }}</span> </h5>
        <div class="card">
              <div class="card-body">
                <ul class="list-group">
                  <li class="list-group-item" v-for="domain in domains" :key="domain">
                    {{ domain }}
                  </li>
                </ul>
              </div>
            </div>
      </div>
    </div>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css"
import "font-awesome/css/font-awesome.css"

export default {
  name: 'App',
  data() {
    return {
      prefixes: ['A', 'B', 'C'],
      sufixes: ['D', 'E', 'F'],
      domains: ['AD', 'AE', 'AF', 'BD', 'BE', 'BF', 'CD', 'CE', 'CF']
    }
  }
}
</script>

<style>
#slogan {
  margin: 30px;
}

#main {
  background: #f1f1f1;
  padding: 2rem;
}
</style>
