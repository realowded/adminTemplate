<template>
    <div class="container">
        <ul class="stepper horizontal" id="horizontal-stepper">
  <li class="step active">
    <div class="step-title waves-effect waves-dark">Step 1</div>
    <div class="step-new-content">
      <div class="row">
        <div class="md-form col-12 ml-auto">
          <input id="email-horizontal" type="email" class="validate form-control" required>
          <label for="email-horizontal">Email</label>
        </div>
      </div>
      <div class="step-actions">
        <button class="waves-effect waves-dark btn btn-sm btn-primary next-step" data-feedback="someFunction21">CONTINUE</button>
      </div>
    </div>
  </li>
  <li class="step">
    <div class="step-title waves-effect waves-dark">Step 2</div>
    <div class="step-new-content">
      <div class="row">
        <div class="md-form col-12 ml-auto">
          <input id="password-horizontal" type="password" class="validate form-control" required>
          <label for="password-horizontal">Your password</label>
        </div>
      </div>
      <div class="step-actions">
        <button class="waves-effect waves-dark btn btn-sm btn-primary next-step" data-feedback="someFunction21">CONTINUE</button>
        <button class="waves-effect waves-dark btn btn-sm btn-secondary previous-step">BACK</button>
      </div>
    </div>
  </li>
  <li class="step">
    <div class="step-title waves-effect waves-dark">Step 3</div>
    <div class="step-new-content">
      Finish!
      <div class="step-actions">
        <button class="waves-effect waves-dark btn-sm btn btn-primary m-0 mt-4" type="button">SUBMIT</button>
      </div>
    </div>
  </li>
</ul>
    </div>
</template>

<script>
    export default {
        mounted() {
            console.log('Component mounted.')
        }
    }

   
</script>
