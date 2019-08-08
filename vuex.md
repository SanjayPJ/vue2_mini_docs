## State Management

**Install vuex using vue-cli**


Inside store.js

```
import ModuleName from './modules/ModuleName'  

export default new Vuex.Store({
    modules: {
        ModuleName,
    }
});
```

inside modules/ModuleName

```
import axios from 'axios'

const state = {
    variableName: value,
};

const getters = {
    getterName: state => state.variableName
};

const actions = {
    async actionName( { commit }, variableName1 ){
        const response = await axios.get('https://jsonplaceholder.typicode.com/todos');
        commit('mutationName', response.data);
    }
};

const mutations = {
    ModuleName: (state, variableName) => {state.variableName = variableName},
}

export default {
    state,
    getters,
    actions,
    mutations
};
```

Inside components

```
<script>
import { mapGetters, mapActions } from 'vuex'; 

export default {
	name: 'Todos',
	methods: {
		...mapActions(['actionName']),
	},
	computed: {
		...mapGetters(['getterName']),
	},
}
</script>
```

**can use getterName inside template**


### 