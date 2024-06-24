<script setup>
const props = defineProps(["valorNumero1", "valorNumero2", "trocarFiltro"]);
</script>

    <template>
    <form>
        <div >
            <input @keyup="props.valorNumero1" class="form-control" type="number" />
            <input @keyup="props.valorNumero2" class="form-control" type="number" />
        </div>
        <div class="col">
            <select @change="props.trocarFiltro" class="form-control text-center">
            <option value="multiplicacao">Multiplicação</option>
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="divisao">Divisão</option>
            </select>
        </div>
    </form>
    </template>