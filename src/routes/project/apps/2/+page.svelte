<h1>Расчет расходов</h1>

<form on:submit|preventDefault={addExpense}>
 <label for="name">Название:</label>
 <input type="text" id="name" bind:value={newName} />
 <label for="amount">Сумма расхода:</label>
 <input type="text" id="amount" bind:value={newAmount} />
 <button type="submit">Добавить</button>
</form>

<table>
 <thead>
  <tr>
   <th>Название</th>
   <th>Сумма расхода (руб.)</th>
   <th>Действия</th>
  </tr>
 </thead>
 <tbody>
  {#each expenses as expense, i}
   <tr>
    <td><div>{expense.name}</div> </td>
    <td><div>{expense.amount}</div> </td>
    <td><button class="deleteBtn" on:click={() => deleteExpense(i)}>Удалить</button></td>
   </tr>
  {/each}
 </tbody>
</table>

<script>
 let expenses = [];

 let newName = '';
 let newAmount = '';

 function addExpense() {
  const obj = {
   name: newName,
   amount: parseInt(newAmount),
  };
  expenses.push(obj);
  expenses = expenses;
  newName = '';
  newAmount = '';
 }

 function deleteExpense(index) {
  expenses.splice(index, 1);
  expenses = expenses;
 }
</script>

<style>
 label {
  display: block;
  margin-bottom: 10px;
 }
 input[type='text'] {
  padding: 5px;
  border: 1px solid #6e6e6e;
  border-radius: 5px;
  margin-right: 10px;
  width: 250px;
 }
 table {
  margin-top: 20px;
  border-collapse: collapse;
  width: 70%;
  height: 140px;
 }
 th,
 td {
  border: 5px solid #999999;
  padding: 12px;
  text-align: center;
 }
 th {
  background-color: #b1b1b1;
 }
 button {
   font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  padding: 5px 10px;
  background-color: #33d175;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
 }
 .deleteBtn {
   font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    padding: 15px 10px;
    background-color: #eb6d6d;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
 }
 h1 {
  font-size: 24px;
  margin-bottom: 20px;
 }
</style>