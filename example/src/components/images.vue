<template>
  <v-container fluid>
    <h4>4 Images</h4>
    <v-form>
      <v-form-base
        id="form-base-images"
        :value="myValue"
        :schema="mySchema"
        :col="6"
        @update:form-base-images="update"
      />
    </v-form>
    
    <!-- Stuff  -->
    <infoline
      :value="myValue"
      :schema="mySchema"
      :path="$options._componentTag"
    />
  </v-container>
</template>

<script>
import VFormBase from '@/components/vFormBase'
import Infoline from '@/components/infoline'
import update from '@/lib'

export default {
  name: 'Images',
  components: { VFormBase, Infoline },
  data () {
    return {
      myValue: {
        image1:'random',
        image2:'random',
        image3:'random',
        image4:'random',
      },
      mySchema: {
        // schema.base prepends value and schema.tail appends
        image1:{ type:'img', base:'https://picsum.photos/512/300?', class:'ma-2' },
        // schema.src 
        image2:{ type:'img', src:'https://picsum.photos/512/300?random',['aspect-ratio']:'1.15' },
        image3:{ type:'img', src:'https://picsum.photos/512/300?random', contain:true, width:250, height:250 },
        image4:{ type:'img', src:'https://picsum.photos/512/300?random', contain:true, class:'ma-2' },
      }
    }
  },
  methods: {
    update
  }
}
</script>
