<template>

    <v-card outlined>
        <v-card-title>
            Housekeeping Assignment Information # {{$route.params.id }}
        </v-card-title>

        <v-card-text>
            <div>
                <!--Number label="HousekeepingId" v-model="item.housekeepingId" :editMode="editMode" @change="change" /-->
            </div>
            <div>
                <Number label="Housekeeper Id" v-model="item.housekeeperId" :editMode="editMode" @change="change" />
            </div>
            <div>
                <Number label="Accomodation Id" v-model="item.accomodationId" :editMode="editMode" @change="change" />
            </div>
            <div>
                <Number label="Room Id" v-model="item.roomId" :editMode="editMode" @change="change" />
            </div>
        </v-card-text>
    </v-card>

</template>

<script>
  const axios = require('axios').default;

  export default {
    name: 'HousekeepingAssignmentInformationViewDetail',
    props: {
      value: Object,
    },
    data: () => ({
        item : [],
    }),
    async created() {
      var params = this.$route.params;
      var temp = await axios.get(axios.fixUrl('/housekeepingAssignmentInformations/' + params.id))

      this.item = temp.data;

    },
    methods: {
    }
  }
</script>

