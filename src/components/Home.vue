<template>
    <div class="container-fluid">
        <div class="jumbotron">
            <h3>Dev.to Weekly Recap!</h3>
            <p>Results between {{ beginDate }} and {{ endDate }}</p>
        </div>
        <div class="row">
            <div class="col-md-6">
                <h3 class="text-primary">Pull Requests</h3>
                <pulls />
            </div>
            <div class="col-md-6">
                <h3 class="text-primary">Issues</h3>
                <issues />
            </div>
        </div>
    </div>
</template>

<script>

import Issues from './Issues'
import Pulls from './Pulls'
import moment from 'moment'

export default {
    name: 'Home',
    data() {
        return {
            beginDate: moment().startOf('isoWeek').format('MM/DD/YYYY'),
            endDate: moment().endOf('isoWeek').format('MM/DD/YYYY')
        }
    },
    components: {
        Issues,
        Pulls
    }
}
</script>
