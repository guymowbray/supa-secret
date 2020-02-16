<template>
  <div class="hello">
    <h1>{{ date }}</h1>
    <h1>{{ msg }}</h1>
    <br>
    Have Turkey joined the EU yet:
    No
  </div>
</template>

<script src="https://momentjs.com/downloads/moment.js"></script>
<script>
// import '../../static/moment'
import moment from 'moment'
import '../../static/moment-precise-range'
function timeSince () {
  // var startDate = new Date('February 10, 2020 23:59:59')
  // var startDateEpoch = startDate.getTime()
  // var difftime = Date.now() - startDateEpoch

  // var seconds = Math.round(difftime / 1000)
  // var hours = Math.round(difftime / 1000 * 3600)
  // var days = Math.round(difftime / (1000 * 3600 * 24))

  var brexitAnnouncment = moment.utc('2016-05-23T10:28:44+01:00')
  var timesince = moment.preciseDiff(brexitAnnouncment, Date.now())
  return timesince
};
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'since the leave campaign said Turkey is going to join the European Union.',
      date: timeSince()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
