<template>
    <div>
        <p>sumaa</p>
    </div>
  
</template>
<script>
export default{
  name:"sultaN",

  created1() {
  // Simple GET request using fetch
  fetch("https://jsonplaceholder.typicode.com/posts/1/comments")
    .then(response => response.json())
    .then(data => (this.totalVuePackages = data.total));
   
},


async created() {
  // GET request using fetch with async/await
  const response = await fetch("https://jsonplaceholder.typicode.com/posts/1/comments");
  const data = await response.json();
  this.totalVuePackages = data.total;
  
}
,
created0() {
  // GET request using fetch with error handling
  fetch("https://jsonplaceholder.typicode.com/posts/1/comments")
    .then(async response => {
      const data = await response.json();

      // check for error response
      if (!response.ok) {
        // get error message from body or default to response statusText
        const error = (data && data.message) || response.statusText;
        return Promise.reject(error);
   
      }

      this.totalVuePackages = data.total;
    })
    .catch(error => {
      this.errorMessage = error;
      console.error("There was an error!", error);
    });
},

created3() {
  // GET request using fetch with set headers
  const headers = { "Content-Type": "application/json" };
  fetch("https://jsonplaceholder.typicode.com/posts/1/comments", { headers })
    .then(response => response.json())
   

    .then(data => (this.totalVuePackages = data.total));



}

}


</script>