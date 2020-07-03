<template>
<div class="container">
<div class="add-job-container-button">
    <span class="material-icons">add_box</span>
    <p>Adicionar Vaga</p>
</div>
<h1>Visão Geral das Vagas</h1>
<table class="content-table">
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
        <tr>
            <td>Full Stack</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>

        </tr>
        <tr>
            <td>Full Stack</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>

        </tr>
        <tr>
            <td>Full Stack</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>

        </tr>
                <tr>
            <td>Full Stack</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>
            <td>22</td>

        </tr>
    </tbody>
</table>
</div>
</template>

<script>
export default {
    name: "JobsOverview"
}
</script>

<style scoped>
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .container h1 {
        self: left;
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