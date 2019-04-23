<template>
  <div class="treeDrag">
    <draggable :list="data" :options="{ forceFallback: true }">
      <div class="firstLevel" v-for="item in data" :key="item.id">
          <div class="leverFirst">
            {{item.name}}
          </div>
        <draggable :list="item.children" :options="{ forceFallback: true }">
          <div class="SecondLevel" v-for="it in item.children" :key="it.id">
            <div class="leverSecond">
              {{it.name}}
            </div>
             <draggable :list="it.children" :options="{ forceFallback: true }">
                <div class="ThirdLevel" v-for="ele in it.children" :key="ele.id">
                  <div class="leverThird">
                    {{ele.name}}
                  </div>
                </div>
              </draggable>
          </div>
        </draggable>
      </div>
    </draggable>
  </div>
</template>

<script>
import draggable from 'vuedraggable'
export default {
  name: 'treeDrag',
  components: { draggable },
  data () {
    return {
      data: [{
        name: '我是一级分类1',
        id: 1,
        children: [{
          name: '我是二级分类10',
          id: 10,
          children: [{
            name: '我是三级分类100',
            id: 100
          },{
            name: '我是三级分类101',
            id: 101
          }]
        }, {
          name: '我是二级分类11',
          id: 11,
          children: [{
            name: '我是三级分类110',
            id: 110
          },{
            name: '我是三级分类111',
            id: 101
          }]
        }]
      }, {
        name: '我是一级分类2',
        id: 2,
        children: [{
          name: '我是二级分类20',
          id: 20,
          children: [{
            name: '我是三级分类210',
            id: 200
          }]
        }]
      }]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .treeDrag{
    width:300px;
    color: #fff;
    margin-left:auto;
    margin-right:auto;
  }
  .firstLevel{
    background:#D2691E;
  }
  .SecondLevel{
    background:#CD853F;
  }
  .leverThird{
    background:#D2B48C;
  }
  .leverFirst{
    border: 1px solid gray;
    width:300px;
    height:80px;
    line-height: 80px;
    text-align: center;
    font-size:20px;
    margin:1px 0px;
    cursor: move;
  }
  .leverSecond{
    border: 1px solid #BBBBBB;
    width:300px;
    height:60px;
    line-height: 60px;
    text-align: center;
    font-size:16px;
    margin:1px 0px;
    cursor: move;
  }
  .leverThird{
    border: 1px solid #EEEEEE;
    width:300px;
    height:40px;
    line-height: 40px;
    text-align: center;
    font-size:14px;
    margin:1px 0px;
    cursor: move;
  }
</style>
