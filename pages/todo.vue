<template>
	<div class="flex items-center justify-center w-full min-h-screen bg-blue-400">
		<div class="h-[80vh] w-[50%] bg-white rounded-3xl p-4 overflow-auto">
			<h1 class="text-2xl font-bold text-center">ToDo List App</h1>
			<div class="flex items-center w-full gap-3 my-5">
				<input v-model="inputTask" class="w-full h-10 px-2 border border-blue-400 rounded-lg outline-none" type="" name="" placeholder="Add a new task">
				<button  @click="addTask" class="h-10 px-5 bg-blue-400 w-max text-white rounded-xl font-bold">Add</button>
			</div>
			<div class="grid gap-2">
				<div v-for="(task ,index) in tasks" :k="index" class="flex items-center justify-between w-full gap-1">
					<p class="text-lg font-medium cursor-pointer" :class="{ 'line-through': task.isCompleted }"@click="editTask(index)"
					>
				{{ task.task }}</p>
					<div>
						<i @click ="deleteTask(index)" class="text-red-500 fa-solid fa-trash"></i>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	export default{
		data(){
			return{
				inputTask: '',
				tasks: [],
			};
		},
		mounted(){
			this.getTasks();
		},
		methods:{
			getTasks(){
				this.$http.$get("http://localhost:5000/api/tasks").then((res) =>{
					if(res.success){
						this.tasks = res.tasks;
					}
				});
			},
			addTask(){
				if (!this.inputTask) {
					alert("task should be empty");
				}else{
					this.$http.$post("http://localhost:5000/api/tasks" , {
                        body:{
                           task: this.inputTask,
                        },
					})
					.then((res) =>{
					if(res.success){
						this.getTasks();
						this.inputTask = "";
					}
				});
				}
			},
			 editTask(index) {
      this.$http
        .$put("http://localhost:5000/api/tasks/" + this.tasks[index].taskId, {
          body: {
            task: this.tasks[index].task,
            isCompleted: !this.tasks[index].isCompleted,
          },
        })
        .then((res) => {
          if (res.success) {
            this.getTasks();
          }
        });
    },
			 deleteTask(index) {
      this.$http
        .$delete("http://localhost:5000/api/tasks/" + this.tasks[index].taskId)
        .then((res) => {
          if (res.success) {
            this.getTasks();
          }
        });
			},
		},
	};
</script>