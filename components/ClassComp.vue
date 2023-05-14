<template>
    <div >
        <p>{{ name }} {{ age }}</p>
    </div>
</template>

<script>
export default {
  name: 'ClassComp',
  props:{
    name :{
        type: String,
        default: () => 'No name'
    },
    age:{
        type: Number,
        default: () => 0
    },
    salary :{
        type: String,
        default: () => 'No work'
    }
  }

}
</script>