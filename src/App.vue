<template>
  <div>
    <div id="slogan" class="text-center">
      <h1 class="text-center">NameHelper</h1>
      <br />
      <h6 class="text-secondary">
        Name's generator using Vue.js, Graphcl and Node.js
      </h6>
    </div>
    <div id="main">
      <div class="container">
        <div class="row">
          <div class="col-md">
            <h5>
              Prefixes <span class="badge bg-info">{{ prefixes.length }}</span>
            </h5>
            <div class="card">
              <div class="card-body">
                <ul class="list-group">
                  <li
                    class="list-group-item"
                    v-for="prefix in prefixes"
                    :key="prefix"
                  >
                    {{ prefix }}
                  </li>
                </ul>
				<br/>
				<div class="input-group">
					<input type="text" class="form-control" v-model="prefix" v-on:keyup.enter="addPrefix(prefix)" placeholder="Type a prefix">
					<button type="button" class="btn btn-info" v-on:click="addPrefix(prefix)"><span class="fa fa-plus"></span></button>
				</div>
              </div>
            </div>
          </div>
          <div class="col-md">
            <h5>
              Sufixes <span class="badge bg-info">{{ sufixes.length }}</span>
            </h5>
            <div class="card">
              <div class="card-body">
                <ul class="list-group">
                  <li
                    class="list-group-item"
                    v-for="sufix in sufixes"
                    :key="sufix"
                  >
                    {{ sufix }}
                  </li>
                </ul>
				<br/>
				<div class="input-group">
					<input type="text" class="form-control" v-model="sufix" v-on:keyup.enter="addSufix(sufix)" placeholder="Type a sufix">
					<button type="button" class="btn btn-info" v-on:click="addSufix(sufix)"><span class="fa fa-plus"></span></button>
				</div>
              </div>
            </div>
          </div>
        </div>
        <br />
        <h5>
          Domains <span class="badge bg-info">{{ domains.length }}</span>
        </h5>
        <div class="card">
          <div class="card-body">
            <ul class="list-group">
              <li
                class="list-group-item"
                v-for="domain in domains"
                :key="domain"
              >
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
import "bootstrap/dist/css/bootstrap.css";
import "font-awesome/css/font-awesome.css";

export default {
	name: "App",
	data() {
		return {
			prefix: "",
			sufix: "",
			prefixes: [],
			sufixes: [],
			domains: [],
		};
	},
	methods: {
		addPrefix(prefix) {
			this.prefixes.push(prefix);
			this.prefix = "";
			this.generate();
		},
		addSufix(sufix) {
			this.sufixes.push(sufix);
			this.sufix = "";
			this.generate();
		},
		generate() {
			this.domains = [];
			for (const prefix of this.prefixes) {
				for (const sufix of this.sufixes) {
					this.domains.push(prefix + sufix);
				}
			}
		}
	}
};
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
