<template>
  <div class="modal fade" id="myExp" tabindex="-1" role="dialog" aria-labelledby="exampleModalScrollableTitle" aria-hidden="true">
    <div class="modal-dialog modal-dialog-scrollable modal-dialog-centered" role="document">
      <div class="modal-content">
        <div :class="singleExpense.flag" class="modal-header">
          <h5 class="modal-title" id="exampleModalScrollableTitle">{{ singleExpense.title }}</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <div>
            <div class="cart-items">
              <div class="single-item">
                <div class="single-item-details">
                  <h5 class="single-item-name">AMT: {{ singleExpense.amt }}</h5>
                  <p class="single-item-price">DATE: {{ singleExpense.date }}</p>
                  <p class="single-item-price">TIME: {{ singleExpense.time }}</p>
                  <p class="single-item-price">NOTE: {{ singleExpense.note }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary btn-product-red" data-dismiss="modal">Close</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'singleexpense',
  props: ["singleExpense"],
  components: {

  }
}
</script>
<style scoped>
  .btn-product-red {
    padding: 0.7em 3em;
    text-align: center;
    font-size: 16px;
    background: #ff6161;
    color: #ffffff;
    margin-bottom: 24px;
  }
  .bad {
    background: #ff6161
  }
  .bearable {
    background: #FFC36A;
  }
  .reasonable {
    background: #42b983;
  }
</style>
