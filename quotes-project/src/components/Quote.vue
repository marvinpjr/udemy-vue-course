<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot>
                    
                </slot>
            </div>
        </div>
    </div>
</template>
<script>
    export default {};
</script>
<style scoped>
.panel-body {
  font-family: "Arizonia", cursive;
  font-size: 24px;
  color: #6e6e6e;
}

.quote {
  cursor: pointer;
  padding: 10px;
  margin: 5px;
  border: 1px solid darkred;
  border-radius: 10px;
}

.quote:hover {
  background-color: #ffe2e2;
}
</style>


