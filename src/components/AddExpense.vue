<template>
  <div class="expense-form">
    <div class="modal" id="myModal">
      <div class="modal-dialog">
        <div class="modal-content">

          <!-- Modal Header -->
          <div class="modal-header">
            <h4 class="modal-title">Add New Expense</h4>
            <button type="button" class="close" data-dismiss="modal">&times;</button>
          </div>

          <!-- Modal body -->
          <div class="modal-body">
            <div class="row">
              <div class="col-md-12">
                <form>
                  <div class="form-group">
                    <label for="exampleFormControlInput1">Title</label>
                    <input v-model="expense.expTitle" type="text" class="form-control" id="exampleFormControlInput1" required placeholder="Transport">
                  </div>
                  <div class="form-row">
                    <div class="form-group col-md-6">
                      <label for="inputAmt">Amount</label>
                      <div class="input-group mb-2">
                        <div class="input-group-prepend">
                          <div class="input-group-text">#</div>
                        </div>
                        <input v-model="expense.expAmt" type="number" class="form-control" id="inputAmt" required placeholder="Enter Amount">
                      </div>
                    </div>
                    <div class="form-group col-md-6">
                      <label for="inputType">Flag</label>
                      <select v-model="expense.expFlag" class="form-control" id="inputType">
                        <option>Bad</option>
                        <option>Bearable</option>
                        <option>Reasonable</option>
                      </select>
                    </div>
                  </div>
                  <div class="form-row">
                    <div class="form-group col-md-6">
                      <label for="inputDate">Date</label>
                      <input v-model="expense.expDate" type="date" class="form-control" id="inputDate" placeholder="Pick Date">
                    </div>
                    <div class="form-group col-md-6">
                      <label for="inputTime">Time</label>
                      <input v-model="expense.expTime" type="time" class="form-control" id="inputTime" placeholder="Pick Time">
                    </div>
                  </div>
                  <div class="form-group">
                    <label for="addNote">Add Note</label>
                    <textarea v-model="expense.expNote" class="form-control" id="addNote" rows="3" placeholder="Not more than 200 words"></textarea>
                  </div>
                  <button @click.prevent="saveExpense" class="btn btn-success">Save</button>
                </form>
              </div>
            </div>
          </div>

          <!-- Modal footer -->
          <div class="modal-footer">
            <!-- <button type="button" class="btn btn-danger" data-dismiss="modal">Close</button> -->
          </div>

        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'addexpense',
  props: ["expense"],
  data () {
    return {

    }
  },
  methods: {
    saveExpense: function () {
      const item = {
        "title": this.expense.expTitle,
        "amt": `${this.expense.expAmt}`,
        "flag": this.expense.expFlag,
        "date": this.expense.expDate,
        "time": this.expense.expTime,
        "note": this.expense.expNote
      }
      this.$emit('save', item);
      this.expense.expTitle = "";
      this.expense.expAmt = "";
      this.expense.expFlag = "";
      this.expense.expDate = "";
      this.expense.expTime = "";
      this.expense.expNote = "";
    }
  }
}
</script>

<style scoped>
  .expense-form {

  }
  .btn-success {

  }
  select span {

  }
</style>
