# vue store 

### sotre/index.ts:
```ts
const store = new Vuex.Store({
  state: {
    // 状态值
    config: {} as { [key: string]: any }
  },
  getters: {
    // 获取状态的方法
  },
  mutations: {
    // 修改状态的方法
    set_config(state, payload: { [key: string]: any }) {
      state.config[payload.key] = payload.value
    },
  },
  actions: {
    // 提交异步操作的方法
  },
  modules: {
    // 模块
  }
})
```

### vue中读取和修改
```ts
import { useStore } from "vuex";
const store = useStore();

console.log(store.state.config)

store.commit("set_config", { "key": "111", "value": "222" })
```