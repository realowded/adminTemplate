<template>
	<div class="container">
		<div class="row mt-5">
			<div class="col-md-12">
				<div class="card">
					<div class="card-header">
						<h3 class="card-title">Users Management</h3>
						<div class="card-tools">
							<button class="btn btn-success" @click="newModal">Add New <i class="fa fa-user-plus fa-fw"></i>
		 					</button>
						</div>
					</div>
					<!-- /.card-header -->
					<div class="card-body table-responsive p-0">
						<table class="table table-hover">
							<thead>
								<tr>
									<th>ID</th>
									<th>Name</th>
									<th>Email</th>
									<th>Type</th>
									<th>Registered At</th>
									<th>Modify</th>
								</tr>
							</thead>
							<tbody>
								<tr v-for="user in users" :key="user.id">
									<td>{{user.id}}</td>
									<td>{{user.name}}</td>
									<td>{{user.email}}</td>
									<td><span class="tag tag-success">{{user.type | upText}}</span>
									</td>
									<td>{{user.created_at | myDate}}</td>
									<td>
										<a href="#" @click="editModal(user)"> <i class="fa fa-edit blue"> </i></a> 
										/
										<a href="#" id ="delo" @click="deleteUser(user.id)"> <i class="fa fa-trash red"></i></a> 
									</td>
								</tr>
							</tbody>
						</table>
					</div>
					<!-- /.card-body -->
				</div>
				<!-- /.card -->
			</div>
		</div>
		<div class="modal fade" id="addNew" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
			<div class="modal-dialog modal-dialog-centered" role="document">
				<div class="modal-content">
					<div class="modal-header">
						<h5 v-show="editMode" class="modal-title" id="addNew">Edit User</h5>
						<h5 v-show="!editMode" class="modal-title" id="addNew">Add New</h5>
						<button type="button" class="close" data-dismiss="modal" aria-label="Close"> <span aria-hidden="true">&times;</span>
						</button>
					</div>
					<form @submit.prevent="editMode ? updateUser() : createUser()">
						<div class="modal-body">
							<div class="form-group">
								<input v-model="form.name" type="text" name="name" placeholder="Name" class="form-control" :class="{ 'is-invalid': form.errors.has('name') }">
								<has-error :form="form" field="name"></has-error>
							</div>
							<div class="form-group">
								<input v-model="form.email" type="email" name="email" placeholder="Email Adress" class="form-control" :class="{ 'is-invalid': form.errors.has('email') }">
								<has-error :form="form" field="email"></has-error>
							</div>
							<div class="form-group">
								<textarea v-model="form.bio" type="email" name="bio" placeholder="Short Bio for user (Optional)" class="form-control" :class="{ 'is-invalid': form.errors.has('bio') }"></textarea>
								<has-error :form="form" field="bio"></has-error>
							</div>
							<div class="form-group">
								<select v-model="form.type" type="type" name="type" id="type" placeholder="Email Adress" class="form-control" :class="{ 'is-invalid': form.errors.has('type') }">
									<option value="">Select User role</option>
									<option value="admin">Admin</option>
									<option value="user">Standard User</option>
									<option value="author">Author</option>
								</select>
								<has-error :form="form" field="type"></has-error>
							</div>
							<div class="form-group">
								<input v-model="form.password" type="password" name="email" placeholder="Password" class="form-control" :class="{ 'is-invalid': form.errors.has('password') }">
								<has-error :form="form" field="password"></has-error>
							</div>
						</div>
						<div class="modal-footer">
							<button type="button" class="btn btn-danger" data-dismiss="modal">Close</button>
							<button v-show="editMode" type="submit" class="btn btn-success">Update</button>
							<button v-show="!editMode" type="submit" class="btn btn-primary">Create</button>
						</div>
					</form>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
	        data(){
				
	            return {
					editMode: false,
	                users : {},
	                form: new Form({
						id: "",
	                    name: '',
	                    email: '',
	                    password: '',
	                    type: '',
	                    bio: '',
	                    photo: ''
	
	                })
	            }
	        },
	
	        methods: {
				updateUser(){
					this.$Progress.start();
					this.form.put('api/user/'+this.form.id)
					.then(()=> {
						
						$('#addNew').modal('hide');
						Swal.fire(
						'Updated',
						'Information has been Updated.',
						'success'
						)
						this.$Progress.finish();
						Fire.$emit('AfterCreate');
						

					})
					.catch(()=> {
					this.$Progress.fail();
					})


				},
				editModal(user){
					this.editMode = true;
					this.form.reset();
					$('#addNew').modal('show');
					this.form.fill(user);
				},
	        	newModal(){
					this.editMode = false;
					this.form.reset();
					$('#addNew').modal('show');
				},

			 	deleteUser(id){
					Swal.fire({
					title: 'Are you sure?',
					text: "You won't be able to revert this!",
					type: 'warning',
					showCancelButton: true,
					confirmButtonColor: '#3085d6',
					cancelButtonColor: '#d33',
					confirmButtonText: 'Yes, delete it!'
					}).then((result) =>{

						//send request to {
					
						this.form.delete('api/user/'+id).then(()=>{
						
							Swal.fire(
						'Deleted!',
						'Your file has been deleted.',
						'success'
						).then(()=>Fire.$emit('AfterCreate'))

				
					}).catch(()=> {
						swal.fire("Failed", "There was something wrong.","warning");
					});
					});

				},
	            loadUsers(){
	              axios.get('api/user').then(({ data }) => (this.users = data.data));
	            }
	            ,
	            createUser(){
	                
	                this.$Progress.start();
					this.form.post('api/user')
					.then(()=>{
						Fire.$emit('AfterCreate');
					$('#addNew').modal('hide');
					
	                Toast.fire({
	                  type: 'success',
	                  title: 'User Sucesfully Created'
	                });
	                this.$Progress.finish();
					})
					.catch(()=>{

					})
					
	                
	            }
	        },
	          created() {
				this.loadUsers();
				Fire.$on('AfterCreate', () => {
					this.loadUsers();
				});
				//setInterval(()=> this.loadUsers(),3000);
	        }
	    }
</script>