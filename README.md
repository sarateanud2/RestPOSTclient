# RestPOSTcl
Creare Rest Serverului, Get, Post si clientul care adauga si Altul care afisiaza toata lista.

# Pentru adaugare @POST
Client client = Client.create();
WebResource webResource = client.resource("http://localhost:8080/RestServerPOST/run/employee");
ClientResponse response = webResource.accept(MediaType.APPLICATION_JSON).post(ClientResponse.class, employee);

# Pentru afisarea listei @GET
List<Employee> employeeList = Client.create().resource("http://localhost:8080/RestServerPOST/run/employee/allemployees").get(new GenericType<List<Employee>>(){});
		int i = 0;
		for (Employee employee : employeeList) {
			System.out.printf("Employee nr. %d:\n", ++i);
			System.out.printf("First name: %s \n", employee.getFname());
			System.out.printf("Last name: %s \n", employee.getLname());
			System.out.printf("Salary: %d \n", employee.getSalary());
			System.out.println("");
		}
