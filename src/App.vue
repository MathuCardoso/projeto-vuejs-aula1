<script setup>
    import { computed, ref } from "vue";

    const nome = ref("");

    const tamanhos = [
        {
            label: "Pequeno",
            id: "p",
            preco: 25.0,
        },
        {
            label: "Médio",
            id: "m",
            preco: 35.0,
        },
        {
            label: "Grande",
            id: "g",
            preco: 45.0,
        },
    ];
    const sabores = ["Calabresa", "Frango com catupiry", "Portuguesa"];

    const tamanhoSelecionado = ref(tamanhos[0].id);

    const tamanhoEscolhido = computed(() => {
        return tamanhos.find(
            (tamanho) => tamanho.id === tamanhoSelecionado.value,
        );
    });

    const saboresSelecionados = ref([]);
    const quantidade = ref(1);

    function adicionarPizza() {
        if (quantidade.value >= 10) return;
        quantidade.value++;
    }

    function removerPizza() {
        if (quantidade.value <= 1) return;
        quantidade.value--;
    }

    const total = computed(() => {
        return tamanhoEscolhido.value.preco * quantidade.value;
    });

    function enviarPedido() {
        alert("Pedido enviado!");
    }
</script>

<template>
    <main class="container">
        <header class="header">
            <h1>Pizza <span>Vue</span></h1>
            <p>Monte seu pedido e aproveite!</p>
        </header>

        <div class="content">
            <div class="form">
                <label for="nome">Seu nome</label>
                <input
                    type="text"
                    id="nome"
                    v-model="nome"
                    placeholder="Digite seu nome..."
                />

                <label for="tamanho">Tamanho da pizza</label>
                <select id="tamanho" v-model="tamanhoSelecionado">
                    <option :value="tamanho.id" v-for="tamanho in tamanhos">
                        {{ tamanho.label }} - R$ {{ tamanho.preco.toFixed(2) }}
                    </option>
                </select>

                <p class="section-label">Escolha os sabores</p>

                <div class="sabores">
                    <label class="checkbox" v-for="sabor in sabores">
                        <input
                            type="checkbox"
                            :value="sabor"
                            v-model="saboresSelecionados"
                        />
                        <span>{{ sabor }}</span>
                    </label>
                </div>

                <label>Quantidade de pizzas</label>
                <div class="quantidade">
                    <button @click="removerPizza">-</button>
                    <span>{{ quantidade }}</span>
                    <button @click="adicionarPizza">+</button>
                </div>

                <button @click="enviarPedido">Confirmar pedido</button>
            </div>

            <aside class="resumo">
                <h2>Resumo do pedido</h2>

                <div class="resumo-item">
                    <span>Cliente:</span>
                    <span v-if="!nome">Não informado</span>
                    <span v-else>{{ nome }}</span>
                </div>

                <div class="resumo-item">
                    <span>Tamanho:</span>
                    <span>{{ tamanhoEscolhido.label }}</span>
                </div>

                <div class="resumo-item">
                    <span>Sabores:</span>
                    <span v-if="saboresSelecionados.length === 0"
                        >Nenhum sabor selecionado</span
                    >
                    <span v-else>
                        {{ saboresSelecionados.join(", ") }}
                    </span>
                </div>

                <div class="resumo-item">
                    <span>Quantidade:</span>
                    <span>{{ quantidade }}</span>
                </div>

                <div class="total">
                    <span>Total:</span>
                    <strong>R$ {{ total.toFixed(2) }}</strong>
                </div>
            </aside>
        </div>

        <footer class="mensagem">Seu pedido está quase pronto!</footer>
    </main>
</template>
