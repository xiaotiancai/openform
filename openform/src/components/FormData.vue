<template>
    <el-table :data="values" style="width: 100%;">
        <el-table-column
            v-for="(column, key) in columns"
            :key="key"
            :prop="column.property"
            :label="column.label"
            width="180">
            <template slot-scope="scope">
                <div v-if="!Array.isArray(scope.row[scope.column.property])">{{scope.row[scope.column.property]}}</div>
                <div v-if="Array.isArray(scope.row[scope.column.property])">
                    <ul>
                        <li v-for="(value, key) in scope.row[scope.column.property]" :key="key">{{value}}</li>
                    </ul>
                </div>
            </template>
        </el-table-column>
    </el-table>
</template>
<script>
export default {
    data() {
        return {
            "values": [],
            "columns": [],
        }
    },
    async created() {
    },

    methods: {
    }
    
}
</script>