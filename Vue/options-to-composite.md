| options                             | composition                                       |
| ----------------------------------- | ------------------------------------------------- |
| `components: {...}`                 | 사용할 컴포넌트 이름에 맞춰서 import              |
| `data: { NAME: 초기값 } `           | 원시형만 `const NAME = ref(초기값)`               |
|                                     | 참조형(object, array) `const NAME = reactive({})` |
|                                     | script 내 접근 `NAME.value`                       |
| `computed: { NAME() { return V } }` | `const NAME = computed(() => { return V })`       |
|                                     | script 내 접근 `NAME.value`                       |
| `watch: N() {}`                     | `watch(N, () => {})`                              |
| `methods: N(...args) {}`            | `function N(...args) {}`                          |
| `this.$refs.NAME`                   | `const NAME = ref<TYPE \| null>(null)`            |
| `props: {...}`                      | `const props = defineProps({...})`                |
| `emits: [...]`                      | `const emit = defineEmits([...])`                 |

| Pinia            | composition                        |
| ---------------- | ---------------------------------- |
| `mapStores(...)` | `const STORE_NAME = use...Store()` |

| vue-router     | composition                  |
| -------------- | ---------------------------- |
| `this.$route`  | `const route = useRoute()`   |
| `this.$router` | `const router = useRouter()` |

