.form-actions{
    background-color: rgb(33, 37, 33);
    height: 55px;
    display: flex;
    align-items: center;
    justify-content: end;
}

.form-actions button{
    width: 120px;
    border-radius: 8px;
    border: 1px solid transparent;
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color:rgba(87, 153, 228, 0.979);
    margin-right: 15px;
    color: #f8f8f9;
    font-size: 15px;
    cursor: pointer;
    transition: 0.3s ease-in;
}

.form-actions button svg{
    width: 25px;
    margin-left: 10px;
}

.form-actions button:hover{
    background-color: #f8f8f9;
    border-radius: 8px;
    border: 1px solid rgba(87, 153, 228, 0.979);
    color:rgba(87, 153, 228, 0.979);
    font-weight: bold;
}

.form-pdf{
    width: 100%;
    display: flex;
    justify-content: center;
    flex-direction: column;
    margin-top: 30px;
}

.pdf-title{
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.pdf-title h1{
    color: rgb(0, 0, 0);
    font-size: 40px;
    font-weight: bold;
    letter-spacing: 2px;
}

.pdf-title h3{
    color: rgb(0, 0, 0);
    font-size: 28px;
}

.pdf-title .pdf-title-datas{
    width: 60%;
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin-top: 30px;
}

.pdf-title-datas p{
    font-size: 22px;
}

.form-body-pdf{
    width: 100%;
    display: flex;
    justify-content: center;
}

.group-pdf{
    width: 60%;
    display: flex;
    justify-content: center;
    flex-direction: column;
}

.box-pdf{
    margin-top: 20px;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
}

.box-pdf .box-pdf-title{
    background-color: rgb(194, 194, 194);
    width: 100%;
    height: 35px;
    display: flex;
    align-items: center;
}

.box-pdf .box-pdf-title h3{
    margin-left: 20PX;
    color: rgb(0, 0, 0);
    font-size: 20px;
    font-weight: bold;
}

.box-pdf-body{
    background-color: greenyellow;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80px;
}

.box-pdf-body .box-item{
    background-color: red;
    width: 50%;
    display: flex;
    margin-left: 4px;
}

.box-pdf-body .box-item .box-item-box{
    background-color: aqua;
    width: 100%;
    display: flex;
    flex-direction: column;
}

------------------------------------------------------


<template>
  <div class="form-actions">
    <button @click="returnarPag()">
      Retornar
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="bi bi-arrow-left-square" viewBox="0 0 16 16">
        <path fill-rule="evenodd"
          d="M15 2a1 1 0 0 0-1-1H2a1 1 0 0 0-1 1v12a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1V2zM0 2a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v12a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V2zm11.5 5.5a.5.5 0 0 1 0 1H5.707l2.147 2.146a.5.5 0 0 1-.708.708l-3-3a.5.5 0 0 1 0-.708l3-3a.5.5 0 1 1 .708.708L5.707 7.5H11.5z" />
      </svg>
    </button>
    <button @click="exportToPDF()">
      Imprimir
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="bi bi-printer" viewBox="0 0 16 16">
        <path d="M2.5 8a.5.5 0 1 0 0-1 .5.5 0 0 0 0 1z" />
        <path
          d="M5 1a2 2 0 0 0-2 2v2H2a2 2 0 0 0-2 2v3a2 2 0 0 0 2 2h1v1a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2v-1h1a2 2 0 0 0 2-2V7a2 2 0 0 0-2-2h-1V3a2 2 0 0 0-2-2H5zM4 3a1 1 0 0 1 1-1h6a1 1 0 0 1 1 1v2H4V3zm1 5a2 2 0 0 0-2 2v1H2a1 1 0 0 1-1-1V7a1 1 0 0 1 1-1h12a1 1 0 0 1 1 1v3a1 1 0 0 1-1 1h-1v-1a2 2 0 0 0-2-2H5zm7 2v3a1 1 0 0 1-1 1H5a1 1 0 0 1-1-1v-3a1 1 0 0 1 1-1h6a1 1 0 0 1 1 1z" />
      </svg>
    </button>
  </div>
  <div class="form-pdf">
    <div class="pdf-title">
      <h1>Ordem de Serviço N° {{ $route.params.idOrdem }}</h1>
      <h3>{{ $route.params.empresa }}</h3>
      <div class="pdf-title-datas">
        <p>
          <bold>Data de Abertura:</bold> {{ $route.params.dataAbertura }}
        </p>
        <p>
          <bold>Data de Fechamento:</bold> {{ $route.params.dataFechamento }}
        </p>
      </div>
    </div>
    <div class="form-body-pdf">
      <div class="group-pdf">
        <div class="box-pdf">
          <div class="box-pdf-title">
            <h3>Empresa resposável</h3>
          </div>
          <div class="box-pdf-body">
            <div class="box-item">
              <div class="box-item-box">
                <label>Nome</label>
                <p>{{ $route.params.empresa }}</p>
              </div>
              <div class="box-item-box">
                <label>Nome</label>
                <p>{{ $route.params.empresa }}</p>
              </div>
            </div>
            <div class="box-item">
              <div class="box-item-box">
                <label>Nome</label>
                <p>{{ $route.params.empresa }}</p>
              </div>
              <div class="box-item-box">
                <label>Nome</label>
                <p>{{ $route.params.empresa }}</p>
              </div>
            </div>
          </div>
        </div>
        <div class="box-pdf">
          <div class="box-pdf-title">
            <h3>Cliente</h3>
          </div>
          <div class="box-pdf-body">
            <div class="box-item">
              <label>Nome</label>
              <p>{{ $route.params.empresa }}</p>
            </div>
            <div class="box-item">
              <label>CNPJ</label>
              <p>{{ $route.params.empresa }}</p>
            </div>
            <div class="box-item">
              <label>Link de acesso</label>
              <p>{{ $route.params.empresa }}</p>
            </div>
          </div>
        </div>
        <div class="box-pdf">
          <div class="box-pdf-title">
            <h3>Informação Imóvel</h3>
          </div>
          <div class="box-pdf-body">
            <div class="box-item" v-for="(item, index) in checklist" :key="index">
              <label>Nome</label>
              <p>{{ $route.params.empresa }}</p>
              <p>{{ $route.params.empresa }}</p>
              <p>{{ $route.params.empresa }}</p>
            </div>
          </div>
        </div>
        <div class="box-pdf">
          <div class="box-pdf-title">
            <h3>Informação Imóvel</h3>
          </div>
          <div class="box-pdf-body">
            <div class="box-item" v-for="(item, index) in checklist" :key="index">
              <label>Nome</label>
              <p>{{ $route.params.empresa }}</p>
              <p>{{ $route.params.empresa }}</p>
              <p>{{ $route.params.empresa }}</p>
            </div>
          </div>
        </div>

        <div class="input-box">
          <label>Data de Fechamento:</label>

        </div>

        <div class="input-box">
          <label>Empresa:</label>
          <p></p>
        </div>

        <div class="input-box">
          <label>Status:</label>
          <p>{{ $route.params.status }}</p>
        </div>

        <div class="input-box">
          <label>Descrição:</label>
          <p>{{ $route.params.descricao }}</p>
        </div>

        <div class="input-box">
          <label>Segmento:</label>
          <p>{{ $route.params.segmento }}</p>
        </div>

        <div class="input-box">
          <label>Prestador:</label>
          <p>{{ $route.params.prestador }}</p>
        </div>

        <div class="input-box">
          <label for="id_checklist">Checklist:</label>
        </div>

        <div class="checklist-body-items" v-for="(item, index) in checklist" :key="index">
          <ul>
            <li>
              <p>{{ item.checklistPersonalizadoNome }}</p>
            </li>
          </ul>
          <p>{{ item.situacao }}</p>
          <p>{{ item.observacao }}</p>
        </div>

      </div>
    </div>
  </div>
</template>
  
<script setup lang="ts">
import html2pdf from "html2pdf.js"
import { ref, onMounted, defineProps } from 'vue'
import axios from 'axios'
import { useRoute } from 'vue-router';
import '../assets/css/consultaImpress/impressao.css'

const token = localStorage.getItem('token')

// Campos a serem exibidos
const checklist = ref([])
const campo = ref(true)
const idOrdem = ref('')
const idSegmento = ref('')
const observacao = ref('')
const status = ref('')
const nomecheck = ref('')
const route = useRoute();


function exibicaoInput(index: boolean) {
  campo.value = index;
  console.log(idSegmento.value);

}


async function capturarOrdem() {
  let rota = `http://localhost:8080/ordemservico/${route.params.idOrdem}`
  try {
    const response = await axios.get(rota, {
      headers: {
        'Authorization': `Bearer ${token}`
      }
    });
    const ordemData = response.data;
    checklist.value = ordemData.checklistPersonalizados.map(item => {
      return {
        ...item,
        mostrarInput: false, // Inicialmente, o campo de motivo de reprovação está oculto
      };
    });

  } catch (error) {
    console.error('Ocorreu um erro ao coletar as ordens:', error);
  }
}

async function exportToPDF() {
  try {
    const element = document.getElementById('element-to-pdf');
    const pdfOptions = {
      margin: 10,
      filename: 'solicitacao.pdf',
      image: { type: 'jpeg', quality: 0.98 },
      html2canvas: { scale: 2 },
      jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' },
    };

    const pdfBlob = await html2pdf().from(element).set(pdfOptions).outputPdf('blob');
    const url = URL.createObjectURL(pdfBlob);

    // Crie um link para download e clique nele para baixar o PDF
    const a = document.createElement('a');
    a.href = url;
    a.download = 'solicitacao.pdf';
    a.click();
  } catch (error) {
    console.error('Erro ao exportar para PDF:', error);
  }
}

function returnarPag() {
  window.history.back();
}


// Escute o evento personalizado para visualizar a ordem e preencher os campos
onMounted(() => {

  capturarOrdem()

  idOrdem.value = route.params.idOrdem
  idSegmento.value = route.params.idSegmento
  status.value = route.params.status


})

</script>
  
