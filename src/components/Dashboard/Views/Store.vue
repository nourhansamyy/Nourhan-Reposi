<template>
    <div class="row">
      <div class="col-md-12">
        <div class="card">
          <paper-table :title="table1.title" :sub-title="table1.subTitle" :data="table1.data" :columns="table1.columns">

          </paper-table>
        </div>
      </div>

    </div>
</template>
<script>
  import PaperTable from 'components/UIComponents/PaperTable.vue'
  const tableColumns = ['Id', 'Name', 'Price', 'CreatedAt', 'UpdatedAt', 'SellerName']
  const tableData = [{
    id: 1,
    name: ' Black Prom Dress',
    price: '$16.738',
    createdat: '15/2/2018',
    updatedat: '16/2/2018',
    sellername: 'Nourhan Samy'
  },

  {
    id: 2,
    name: 'Clock',
    price: '$26.738',
    createdat: '15/2/2018',
    updatedat: '16/2/2018',
    sellername: 'Passant Omar'
  },

  {
    id: 2,
    name: 'Sweater',
    price: '$346.738',
    createdat: '15/2/2018',
    updatedat: '16/2/2018',
    sellername: 'Khaled EL Shimi'
  },

  {
    id: 3,
    name: 'Pantalone',
    price: '$134.738',
    createdat: '15/2/2018',
    updatedat: '16/2/2018',
    sellername: 'Rawan shehab'
  },
  {
    id: 3,
    name: 'Dog',
    price: '$176.738',
    createdat: '15/2/2018',
    updatedat: '16/2/2018',
    sellername: ' Mina Ramsis'
  }
]

  export default {
    components: {
      PaperTable
    },
    data () {
      return {
        table1: {
          title: ' Component 1 Olx',
          subTitle: 'Here is the products for this table',
          columns: [...tableColumns],
          data: [...tableData]
        },
        table2: {
          title: 'Table on Plain Background',
          subTitle: 'Here is a subtitle for this table',
          columns: [...tableColumns],
          data: [...tableData]
        }
      }
    }
  }

</script>
<style>

</style>
