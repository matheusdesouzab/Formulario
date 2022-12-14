<template>
    <div class="container-fluid border border-dark">
        <div class="row">
            <div class="col-6 bg-light p-4 ">
                <span class="fs-4 fw-bold">ENTRADA DE DADOS</span>
                <hr>
                <form @reset.prevent="resetar()">
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Nome:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-model="form.nome">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">E-mail:</label>
                        <div class="col">
                            <input type="email" class="form-control" v-model.trim="form.email">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Senha:</label>
                        <div class="col">
                            <input type="password" class="form-control" v-model="form.senha">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Idade:</label>
                        <div class="col">
                            <input type="number" class="form-control" v-model.number="form.idade">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Gênero:</label>
                        <div class="col">
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" value="feminino" v-model="form.genero">
                                <label class="form-check-label">
                                    Feminino
                                </label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" value="masculino" v-model="form.genero">
                                <label class="form-check-label">
                                    Masculino
                                </label>
                            </div>
                        </div>
                    </div>

                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Licença:</label>
                        <div class="col">
                            <div class="form-check form-switch">
                                <input class="form-check-input" type="checkbox" v-model="form.licenca" true-value="sim"
                                    false-value="não">
                                <label class="form-check-label">Li e aceito os termos</label>
                            </div>
                        </div>
                    </div>

                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Interesses:</label>
                        <div class="col">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" value="JavaScript"
                                    v-model="form.interesses">
                                <label class="form-check-label">
                                    JavaScriot
                                </label>
                            </div>
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" value="VueJs" v-model="form.interesses">
                                <label class="form-check-label">
                                    VueJS
                                </label>
                            </div>
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" value="Angular"
                                    v-model="form.interesses">
                                <label class="form-check-label">
                                    Angular
                                </label>
                            </div>
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" value="NodeJs"
                                    v-model="form.interesses">
                                <label class="form-check-label">
                                    NodeJS
                                </label>
                            </div>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Telefone:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-maska="'(##) #####-####'" v-model="form.telefone">
                            <small class="text-muted">Formato: {{ form.telefone }}</small>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">CEP:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-maska="'#####-###'" v-model="form.cep">
                            <small class="text-muted">Formato: {{ form.cep }}</small>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">CNPJ:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-maska="'##.###.###/####-##'" v-model="form.cnpj">
                            <small class="text-muted">Formato: {{ form.cnpj }}</small>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">CPF:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-maska="'###.###.###-##'" v-model="form.cpf">
                            <small class="text-muted">Formato: {{ form.cpf }}</small>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Data:</label>
                        <div class="col">
                            <input type="date" class="form-control" v-model="form.data">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Data/hora local:</label>
                        <div class="col">
                            <input type="datetime-local" class="form-control" v-model="form.dataHora">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Mês:</label>
                        <div class="col">
                            <input type="month" class="form-control" v-model="form.mes">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Semana:</label>
                        <div class="col">
                            <input type="week" class="form-control" v-model="form.semana">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Hora:</label>
                        <div class="col">
                            <input type="time" class="form-control" v-model="form.hora">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Cartão de credito:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-maska="'#### #### #### ####'"
                                v-model="form.cartaoDeCredito">
                            <small class="text-muted">Formato: {{ form.cartaoDeCredito }}</small>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Placa Veículo:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-maska="'AAA-####'" v-model="form.placaVeiculo">
                            <small class="text-muted">Formato: {{ form.placaVeiculo }}</small>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Placa Veículo Mercosul:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-maska="'AAA#A##'"
                                v-model="form.placaVeiculoMercosul">
                            <small class="text-muted">Formato: {{ form.placaVeiculoMercosul }}</small>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">RG:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-maska="'#*-X'" v-model="form.rg">
                            <small class="text-muted">Formato: {{ form.rg }}</small>
                        </div>
                    </div>
                 
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Cor:</label>
                        <div class="col">
                            <input type="color" class="form-color" v-model="form.cor">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Valor limite:</label>
                        <div class="col">
                            <input type="range" class="form-range" min="0" max="100" step="1" v-model="form.alcance">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Escondido:</label>
                        <div class="col">
                            <input type="hidden" class="form-control" v-model="form.escondido">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Upload:</label>
                        <div class="col">
                            <input type="file" class="form-control" @change="selecionarArquivos($event)" multiple>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Descrição:</label>
                        <div class="col">
                            <textarea class="form-control" rows="3" v-model="form.descricao"></textarea>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Cursos</label>
                        <div class="col">
                            <select name="" id="" class="form-select" v-model="form.curso">
                                <option value="">-- Selecione uma opção --</option>
                                <option v-for="curso in cursos" :key="curso.id" :value="curso.id">{{ curso.curso }}
                                </option>
                            </select>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Descrição:</label>
                        <div class="col">
                            <!-- <input-estrelas :numero-estrelas="5" @avaliacao="form.avaliacao = $event"></input-estrelas> -->
                            <input-estrelas :numero-estrelas="5" v-model:avaliar="form.avaliacao"></input-estrelas> 
                        </div>
                    </div>
                    <hr>
                    <div class="mb-3 row">
                        <div class="col d-flex justify-content-between">
                            <button class="btn btn-secondary" type="reset">Limpar</button>
                            <button class="btn btn-success" type="button">Enviar (btn)</button>
                            <button class="btn btn-success" type="submit">Enviar (submit)</button>
                        </div>
                    </div>

                </form>
            </div>

            <div class="col-6 text-white bg-secondary p-4">
                <span class="fs-4 fw-bold">ESTADO DO OBJETO</span>
                <hr>
                <div class="mb-3 row">
                    <span>Nome: {{ form.nome }}</span>
                </div>
                <div class="mb-3 row">
                    <span>E-mail: {{ form.email }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Senha: {{ form.senha }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Idade: {{ form.idade }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Gênero: {{ form.genero }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Licença: {{ form.licenca }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Interesses: {{ form.interesses }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Telefone: {{ form.telefone }}</span>
                </div>
                <div class="mb-3 row">
                    <span>CEP: {{ form.cep }}</span>
                </div>
                <div class="mb-3 row">
                    <span>CNPJ: {{ form.cnpj }}</span>
                </div>
                <div class="mb-3 row">
                    <span>CPF: {{ form.cpf }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Data: {{ $moment(form.data).format('DD/MM/YYYY') }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Data/hora local: {{ $moment(form.dataHora).format('dddd') }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Mês: {{form.mes}}</span>
                </div>
                <div class="mb-3 row">
                    <span>Semana: {{ form.semana }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Hora: {{ form.hora }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Cartão de credito: {{ form.cartaoDeCredito }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Placa de veículo: {{ form.placaVeiculo }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Placa de veículo Mercosul: {{ form.placaVeiculoMercosul }}</span>
                </div>
                <div class="mb-3 row">
                    <span>RG: {{ form.rg }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Cor: {{ form.cor }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Valor limite: {{ form.alcance }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Escondido: {{ form.escondido }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Upload:</span>
                    <ul>
                        <li v-for="(arquivo, index) in form.arquivos" :key="index">{{ arquivo.name }}</li>
                    </ul>
                </div>
                <div class="mb-3 row">
                    <span>Descrição:</span>
                    <div style="white-space: pre">{{ form.descricao }}</div>
                </div>
                <div class="mb-3 row">
                    <span>Curso: {{ form.curso }}</span>
                </div>
                <div class="mb-3 row">
                    <span>Avaliação: {{ form.avaliacao }}</span>
                </div>
            </div>
        </div>

    </div>

</template>

<script>
import InputEstrelas from './InputEstrelas.vue'

export default {
    name: 'FormularioComponent',
    components: {
        InputEstrelas
    },
    data: () => ({
        cursos: [
            { id: 1, curso: 'Banco de Dados Relacionais' },
            { id: 2, curso: 'Desenvolvimento Web Completo' },
            { id: 3, curso: 'Node Completo' },
            { id: 4, curso: 'Laravel' }
        ],
        form: {},
        formEstadoInicial: {
            nome: '',
            email: '',
            senha: '',
            interesses: [],
            genero: '',
            telefone: '',
            cep: '',
            cpf: '',
            cnpj: '',
            cartaoDeCredito: '',
            placaVeiculo: '',
            placaVeiculoMercosul: '',
            rg: '',
            data: '',
            dataHora: '',
            mes: '',
            semana: '',
            hora: '',
            cor: '#e5e5e5',
            alcance: 5,
            escondido: '',
            arquivos: [],
            descricao: '',
            curso: '',
            avaliacao: ''
        }
    }),
    methods: {
        selecionarArquivos(event) {
            this.form.arquivos = event.target.files
        },
        resetar(){
            this.form = Object.assign({}, this.formEstadoInicial)
        }
    },
    created(){
        this.resetar()
    }
}
</script>
