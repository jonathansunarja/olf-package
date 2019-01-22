<template>
    <div id="keydata-container" class="tools-panel panel">
        <table>
            <thead>
                <th>
                    <slot name="title"></slot>
                </th>
                <th style="text-align: right">
                    <button class="edit-btn" v-if="editable">Edit</button>
                </th>
            </thead>
            <tbody>
                <tr v-for="item in data">
                    <td colspan="2">
                        {{item.key}} 
                        <span class="float-right">
                            <span v-if="item.displayValueMovement">
                                <i class="fas fa-caret-up" v-if="item.value > 0"></i>
                                <i class="fas fa-caret-down" v-else-if="item.value < 0"></i>
                                <i class="fas fa-minus" v-else></i>
                                &nbsp;
                            </span>
                            {{item.value}}
                        </span>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    props: {
        editable: Boolean,
        data: Array
    }
}
</script>

<style lang="scss" scoped>
/* Colour definitions */
$colour-green-primary: #18E084;
$colour-green-dark: #1BD981;
$colour-white: #ffffff;

.panel {
    border-radius: 15px;

    table {
        width: 100%;

        th {
            padding: 10px 15px;
            vertical-align: middle;
        }
        
        tr {
            border-top: 2px solid;

            td {
                padding: 5px 15px;
            }
        }
    }
}

button {
    border-radius: 15px;
    cursor: pointer;
    font-weight: bold;
    font-size: 9pt;
    padding: 10px 15px;
    margin: 10px auto;
    border: 0;
    background-color: transparent;
}

a:hover, button:hover {
    filter: brightness(105%);
}

#keydata-container {
    background-color: $colour-green-primary;
    color: $colour-white;

    tr {
        border-top-color: $colour-green-dark;

        td {
            font-weight: bold;
        }
    }

    button {
        margin: 0px!important;
    }
}

.edit-btn {
    border: 2px solid $colour-white;
    color: $colour-white;
}

.float-right {
    font-weight: normal;
}
</style>
