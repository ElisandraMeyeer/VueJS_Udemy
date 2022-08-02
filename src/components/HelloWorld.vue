
<template>
  <div class="col-12 md:col-4">
    <a href="https://www.digitro.com/" target="_blank">
      <img src="/logo.png" class="logo" alt="Vite logo" />
    </a>

    <div class="p-inputgroup">
      <span class="p-inputgroup-addon">
        <i class="pi pi-user"></i>
      </span>
      <InputText id="inputNome" placeholder="Nome completo" />
    </div>

    <div class="col-12 md:col-4">
      <div class="p-inputgroup">
        <span class="p-inputgroup-addon">C</span>

        <InputText id="inputCargo" placeholder="Cargo" />
      </div>
    </div>

    <div class="col-12 md:col-4">
      <div class="p-inputgroup">
        <span class="p-inputgroup-addon">I</span>
        <InputText id="inputIdade" placeholder="Idade" />
      </div>
    </div>

    <div class="col-12 md:col-4">
      <div class="p-inputgroup">
        <span class="p-inputgroup-addon">S</span>
        <InputText id="inputSalario" placeholder="Salário" />
      </div>
    </div>

    <div class="col-12 md:col-4">
      <div class="p-inputgroup">
        <span class="p-inputgroup-addon">B</span>
        <InputText id="inputBeneficio" placeholder="Benefício" />
      </div>
    </div>

    <Button
      @click="adicionarFuncionario()"
      label="Cadastrar"
      class="p-button-raised p-button-rounded"
    />
  </div>
  <hr />
  <h4>Último funcionário cadastrado</h4>
  <p v-if="funcionarios.length > 0">
    Nome: {{ funcionarios[funcionarios.length - 1].nome }} <br />
    Cargo: {{ funcionarios[funcionarios.length - 1].cargo }} <br />
    Idade: {{ funcionarios[funcionarios.length - 1].idade }} <br />
    Salário: {{ funcionarios[funcionarios.length - 1].salario }} <br />
    Beneficio: {{ funcionarios[funcionarios.length - 1].beneficio }} <br />
  </p>
  <hr />
  <h4>Funcionários com benefício vale transporte</h4>
  <p v-for="p in funcionarios" :key="p.nome">
    {{ p.beneficio == "Vale transporte" ? p.nome : "" }}
  </p>
  <hr />
  <h4>Funcionários cadastrados</h4>
  <p v-for="p in funcionarios" :key="p.nome">{{ p.nome }}</p>
  <hr />
  <input type="text" v-model="teste" />
  <p>{{ teste }}</p>

  <input type="radio" value="f" v-model="sexo" />Feminino
  <input type="radio" value="m" v-model="sexo" />Masculino
  <br />
  {{ sexo }}
  <hr>
  <select v-model="plano">
    <option value="" disabled>Selecione um plano</option>
    <option value="1">Básico 1</option>
    <option value="2">Básico 2</option>
    <option value="3">Master</option>
  </select>
  <br>
  {{ plano }}
  <hr>
  <input type="checkbox" value="100" v-model="doencas">Asma
  <input type="checkbox" value="101" v-model="doencas">Diabetes tipo 1
  <input type="checkbox" value="102" v-model="doencas">Rinite
  <br>

  <p>{{ doencas }}</p>

  <textarea v-model="diagnostico"></textarea>
  <br>
  {{ diagnostico }}
  <hr>
  <span>Paciente</span><input type="text" v-model="paciente">
  <br>
  <ul>
    <li v-for="p in lista" :key="p.nome">{{ p.nome }} , {{ p.idade }}</li>
  </ul>




</template>

<script>
export default {
  name: 'HelloWorld',
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
</style>
