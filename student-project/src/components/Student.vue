<template>
  <div class="new-component">
   <img src={{pic}}/>
   <h2>{{firstName}} {{lastName}}</h2>
   <p>Email: {{email}} {{pic}}</p>
   <p>Skill: {{skill}}</p>
   <p>Average: </p>
    
 </div>
</template>

<script>
export default {
  name: 'Student',

  props: ['firstName', 'email', 'city', 'company', 'lastName', 'pic', 'skill'],
}
</script>