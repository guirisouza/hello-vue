<template>
<div class="container">
<div class="add-job-container-button" v-on:click="toggleForm()">
    <span class="material-icons" v-if="showForm == false">keyboard_arrow_down</span>
    <span class="material-icons" v-if="showForm == true">keyboard_arrow_up</span>
    <p>{{tittleButton}}</p>
</div>
<div class="container-job">
    <div class="container-job-form" v-if="showForm == true">
        <div class="col-1">
            <div class="input-box-text">
                <span class="text">Nome da Vaga</span>
                <input v-model="jobForm.name" type="text" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">Hunting</span>
                <input v-model="jobForm.hunting" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">Indicação</span>
                <input v-model="jobForm.recommendation" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">Não Contatados</span>
                <input v-model="jobForm.contactedTrys" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">Contatados</span>
                <input v-model="jobForm.contacted" type="number" name="" required="">
            </div>
        </div>
        <div class="col-1">
            <div class="input-box-number">
                <span class="text">Sem Interesse</span>
                <input v-model="jobForm.notInterested" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">1 Fase</span>
                <input v-model="jobForm.firstPhase" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">2 Fase</span>
                <input v-model="jobForm.secondPhase" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">Classificado</span>
                <input v-model="jobForm.classified" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">Desclassificado</span>
                <input v-model="jobForm.declassified" type="number" name="" required="">
            </div>
        </div>
        <div class="col-1">
            <div class="input-box-number">
                <span class="text">Em negociação</span>
                <input v-model="jobForm.inNegociation" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">Oferta</span>
                <input v-model="jobForm.offer" type="number" name="" required="">
            </div>
            <div class="input-box-number">
                <span class="text">Contratação</span>
                <input v-model="jobForm.hiring" type="number" name="" required="">
            </div>
        </div>

    </div>
    <div class="instruction-form" v-if="showForm == true">
        <p>Para inserir uma nova vaga, por favor preencher o formulário ao lado e clicar em salvar</p>
        <div class="add-job-container-button" @click="submitForm()">
            <span class="material-icons">add_box</span>
        <p>Salvar</p>
</div>
    </div>
</div>
<h1 v-if="jobs.length > 0">Visão Geral das Vagas</h1>
<table v-if="jobs.length > 0" class="content-table">
    <thead>
        <tr>
            <th>Vaga</th>
            <th>Total</th>
            <th>Hunting</th>
            <th>Indicação</th>
            <th>Inscrição</th>
            <th>N Contatado</th>
            <th>Contatado</th>
            <th>S Interesse</th>
            <th>1a Fase</th>
            <th>2a Fase</th>
            <th>Classificado</th>
            <th>Desclassificado</th>
            <th>Em negociação</th>
            <th>Oferta</th>
            <th>Contratação</th>

        </tr>
    </thead>
    <tbody>
        <tr v-for="job in jobs" :key="job.name">
            <td>{{job.name}}</td>
            <td>{{job.total}}</td>
            <td>{{job.hunting}}</td>
            <td>{{job.recommendation}}</td>
            <td>{{job.subscription}}</td>
            <td>{{job.contactedTrys}}</td>
            <td>{{job.contacted}}</td>
            <td>{{job.notInterested}}</td>
            <td>{{job.firstPhase}}</td>
            <td>{{job.secondPhase}}</td>
            <td>{{job.classified}}</td>
            <td>{{job.declassified}}</td>
            <td>{{job.inNegociation}}</td>
            <td>{{job.offer}}</td>
            <td>{{job.hiring}}</td>

        </tr>
    </tbody>
</table>
</div>
</template>

<script>
export default {
    name: "JobsOverview",
    data() {
        return {
            jobs: [],
            showForm: false,
            tittleButton: 'Adicionar Vaga',
            jobForm: {
                name: '',
                hunting: 0,
                recommendation: 0,
                subscription: 0,
                contactedTrys: 0,
                contacted: 0,
                notInterested: 0,
                firstPhase: 0,
                secondPhase: 0,
                classified: 0,
                declassified: 0,
                inNegociation: 0,
                offer: 0,
                hiring: 0,
            }
        }
    },
    methods: {
        toggleForm: function() {
            console.log('teste')
            this.showForm = !this.showForm
            if (this.showForm == false){
                this.tittleButton = "Adicionar Vaga"
            } else {
                this.tittleButton = "Fechar"
            }
        },
        submitForm: function() {
            const job = {...this.jobForm}
            this.jobs.push(job)
            this.showForm = false
            this.tittleButton = "Adicionar Vaga"
            this.jobForm = {name: '', 
                hunting: 0, 
                recommendation: 0, 
                subscription: 0,
                contactedTrys: 0,
                contacted: 0,
                notInterested: 0,
                firstPhase: 0,
                secondPhase: 0,
                classified: 0,
                declassified: 0,
                inNegociation: 0,
                offer: 0,
                hiring: 0,
            }
        }
    }
}
</script>

<style scoped>

    .col-1 {
        display: flex;
        flex-direction: column;
        margin-top: 23px;
        margin-left: 30px;;
    }


    .container {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        width:100%;
    }

    .container-job {
        display: flex;
        width: 90%;
    }

    .instruction-form {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        margin-top: 30px;
        margin-left: 30px;
        border-left: 1px solid #dddddd;
        width: 300px;
        height: 300px;
    }

    .instruction-form p {
        text-align: left;
        margin-left: 30px;
    }

    .container-job-form {
        display: flex;
        align-self: start;
        align-content: center;
        justify-content: center;
        width: 900px;
        margin-top: 30px;
        background-color: rgba(0, 152, 121, 0.4);
        height: 300px;
    }

    .input-box-text {
        display: flex;
        flex-direction: column;
        width: 200px
    }

    .input-box-number {
        display: flex;
        flex-direction: column;
        width: 200px
    }

    .container h1 {
        align-self: left;
    }

    .content-table {
        border-collapse: collapse;
        font-size: 0.9em;
        width: 90%;
        border-radius: 6px 6px 0 0;
        overflow: hidden;
        box-shadow: 0 0 20px rgba(0,0,0,0.15);
    }

    .content-table thead tr {
        background-color: #009879;
        color: #fff;
        text-align: left;
        font-weight: bold;
    }

    .content-table tbody td {
        text-align: left;
    }

    .content-table tbody tr {
        border-bottom: 1px solid #dddddd;
    }

    .content-table tbody tr:nth-last-of-type(even) {
        background-color: #f3f3f3;
    }

    .content-table tbody tr:last-of-type {
        border-bottom: 3px solid #009879;
    }

    .content-table th,
    .content-table td {
        padding: 5px 7px;
    }

    .content-table tbody tr:hover {
        font-weight: bold;
        color:#009879;
    }

    .add-job-container-button {
        height: 50px;
        width: 140px;
        border-radius: 7px;
        background-color: #009879;
        display: flex;
        align-items: center;
        justify-content: center;
        align-self: start;
        margin-left: 80px;
        color: white;
        cursor: pointer;
        transition: 0.2s;
    }

    .add-job-container-button:hover {
        box-shadow: 0 0 20px rgba(0,0,0,0.15);
    }




</style>