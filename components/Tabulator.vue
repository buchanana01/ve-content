<template>
    <div id="table" :style="containerStyle"></div>
</template>

<script>

const dependencies = [
    'https://unpkg.com/tabulator-tables@4.9.1/dist/css/tabulator.min.css',
    'https://unpkg.com/tabulator-tables@4.9.1/dist/js/tabulator.min.js'
]

module.exports = {
    name: 'Tabulator',
    props: {
      items: Array,
      width: Number,
      height: Number
    },
    computed: {
        containerStyle() { return { width: `${this.width}px`, height: `${this.height}px`} },
        input() { return this.items[0].data || this.items[0].url }
    },
    mounted() {
        console.log(this.$options.name, this.items)
        this.loadDependencies(dependencies, 0, this.init)
    },
    methods: {
        init() {
            fetch(this.input).then((resp) => resp.text())
            .then((delimitedDataString) => {
                const delimiter = this.input.split(".").pop() == 'tsv' ? '\t' : ',';
                const data = this.toObjArray(delimitedDataString, delimiter)
                console.log(data)
                new Tabulator('#table', {
                    data: data.data, 
                    height: this.height,
                    layout: 'fitColumns',
                    columns: data.fields.map(field => { return { title: field, field }})
                })
            })
        },
        toObjArray(delimitedData, delimiter) {
            const data = { fields: [], data: [] }
            delimiter = delimiter || '\t'
            const lines = delimitedData.split('\n').filter(line => line.trim() !== '')
            if (lines.length > 1) {
                data.fields = lines[0].split(delimiter).map(key => key.trim());
                lines.slice(1).forEach(line => {
                    let obj = {}
                    line.split(delimiter)
                        .map(value => value.trim())
                        .forEach((value, i) => obj[data.fields[i]] = value)
                    data.data.push(obj)
                })
            }
            return data
        }
    }
  }
</script>

<style scoped>
</style>