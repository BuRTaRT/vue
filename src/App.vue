<template>
    <div class="wrapper">
        <div class="modal-window" v-if="visible">
            <div class="w100"><i class="fas fa-times close-modal" @click="visible=!visible"></i></div>
            <div class="inp-container">
                <div class="inp-name">Call controll</div>
                <input type="text" v-model="temp['Call controll']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Read</div>
                <input type="text" v-model="temp['Read']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Sound/Autocoll</div>
                <input type="text" v-model="temp['Sound/Autocol']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Truck</div>
                <input type="text" v-model="temp['Truck']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Origin</div>
                <input type="text" v-model="temp['Origin']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Destination</div>
                <input type="text" v-model="temp['Destination']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Pickup</div>
                <input type="text" v-model="temp['Pickup']">
            </div>
            <div class="inp-container">
                <div class="inp-name">DH-O</div>
                <input type="text" v-model="temp['DH-O']">
            </div>
            <div class="inp-container">
                <div class="inp-name">DH-D</div>
                <input type="text" v-model="temp['DH-D']">
            </div>
            <div class="inp-container">
                <div class="inp-name">F/P</div>
                <input type="text" v-model="temp['F/P']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Length</div>
                <input type="text" v-model="temp['Length']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Weight</div>
                <input type="text" v-model="temp['Weight']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Trip</div>
                <input type="text" v-model="temp['Trip']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Alarm</div>
                <input type="text" v-model="temp['Alarm']">
            </div>
            <div class="inp-container">
                <div class="inp-name">Actions</div>
                <input type="text" v-model="temp['Actions']">
            </div>
            <div class="w100"></div>
            <input class="btn-success modal-btn" type="button" value="confirm" @click="modalConfirm">
        </div>
        <p>Post Trucks</p>
        <div class="btn-container">
            <i class="fas fa-play-circle" @click="randomElems(1000)"></i>
            <div class="v-line">

            </div>
            <div class="icon-container plus" @click="visible=!visible">
                <i class="fas fa-plus"></i>
                <span>New</span>
            </div>
            <div class="icon-container delete" @click="deleteAll(table1)">
                <i class="fas fa-times"></i>
                <span>Delete All</span>
            </div>
            <div class="icon-container Repost">
                <i class="fas fa-redo-alt"></i>
                <span>Repost All</span>
            </div>

        </div>
        <table class="table1" border="bordered">
            <tr>
                <th>Call controll</th>
                <th>Read</th>
                <th>Sound/Autocol</th>
                <th>Truck</th>
                <th>Origin</th>
                <th>Destination</th>
                <th>Pickup</th>
                <th>DH-O</th>
                <th>DH-D</th>
                <th>F/P</th>
                <th>Length</th>
                <th>Weight</th>
                <th>Trip</th>
                <th>Alarm</th>
                <th>Actions</th>
            </tr>
            <tr v-for="item in table1">
                <td v-for="i in item">{{ i }}</td>
            </tr>
        </table>
        <div class="results">
            <div class="results-result">Search Results: {{ count }}</div>
            <div class="btn-container">
                <div class="icon-container">
                    <i class="fas fa-redo-alt Undo"></i>
                    <span>Undo</span>
                </div>
                <div class="icon-container">
                    <i class="far fa-times-circle" @click="deleteAll(table2)"></i>
                    <span>Clear</span>
                </div>
            </div>
        </div>
        <div class="wrap">
            <table class="table2">
                <tr>
                    <th>Rate</th>
                    <th>F</th>
                    <th>Source</th>
                    <th>Age</th>
                    <th>Avail</th>
                    <th>Truck</th>
                    <th>Truck-O</th>
                    <th>DH-O</th>
                    <th>F/P</th>
                    <th>Origin</th>
                    <th>Trip</th>
                    <th>DH-D</th>
                    <th>Truck-D</th>
                    <th>Length</th>
                    <th>Weight</th>
                    <th>Company</th>
                    <th>Phone</th>
                </tr>
                <tr v-for="item in table2">
                    <td v-for="i in item">{{ i }}</td>
                </tr>
            </table>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            visible: false,
            temp: {
                "Call controll": "",
                "Read": "",
                "Sound/Autocol": "",
                "Truck": "",
                "Origin": "",
                "Destination": "",
                "Pickup": "",
                "DH-O": "",
                "DH-D": "",
                "F/P": "",
                "Length": "",
                "Weight": "",
                "Trip": "",
                "Alarm": "",
                "Actions": ""
            },
            table1: [],
            table2: [{
                    "Rate": "3150",
                    "F": "Yes",
                    "Source": "Dat",
                    "Age": "00:01",
                    "Avail": "",
                    "Truck": "",
                    "Truck-O": "",
                    "DH-O": "",
                    "F/P": "",
                    "Origin": "",
                    "Trip": "",
                    "DH-D": "",
                    "Truck-D": "",
                    "Length": "",
                    "Weight": "",
                    "Company": "",
                    "Phone": "",
                },
                {
                    "Rate": "",
                    "F": "No",
                    "Source": "Dat",
                    "Age": "00:02",
                    "Avail": "",
                    "Truck": "",
                    "Truck-O": "",
                    "DH-O": "",
                    "F/P": "",
                    "Origin": "",
                    "Trip": "",
                    "DH-D": "",
                    "Truck-D": "",
                    "Length": "",
                    "Weight": "",
                    "Company": "",
                    "Phone": "",
                }
            ]
        }
    },
    methods: {
        modalConfirm() {
            this.table1.push(this.temp);
            console.log(this.table1);
            this.temp = {
                "Call controll": "",
                "Read": "",
                "Sound/Autocol": "",
                "Truck": "",
                "Origin": "",
                "Destination": "",
                "Pickup": "",
                "DH-O": "",
                "DH-D": "",
                "F/P": "",
                "Length": "",
                "Weight": "",
                "Trip": "",
                "Alarm": "",
                "Actions": ""
            }
        },
        deleteAll(table) {
            table.splice(0, table.length);
        },
       
    },
    computed: {
        count(){
         return this.table2.length;
        }
    },
    components: {}
};

</script>

<style scoped>
i {
    font-style: normal;
}

i {
    color: green;
    font-size: 35px;
}

.fa-play-circle {
    cursor: pointer;
}

.wrapper {
    background-color: #C5DBEC;
    min-height: 100vh;
}

.wrapper {
    padding: 20px;
}

.wrapper p {
    font-size: 22px;
}

.btn-container,
label {
    display: flex;
    align-items: center;
}

.btn-container span {
    margin: 0px 5px;
}

.v-line {
    height: 38px;
    width: 2px;
    background-color: black;
    margin: 0px 10px;
}

.fa-times {
    color: red;
}

.fa-redo-alt {
    color: gray;
}

.icon-container {
    display: flex;
    align-items: center;
    cursor: pointer;
}

table {
    width: 100%;
}

.table1 {
    margin: 30px 0px;
}

.table2 {
    margin-top: 5px;
}

th {
    padding: 5px 10px;
    background-color: #454345;
    color: white;
    font-weight: 400;
    border: 1px solid white;
    flex-grow: 1;
}

td {
    background-color: white;
    color: black;
    padding: 5px 10px;
    border: 1px solid lightgray;
    height: 35px;
}

.Undo {
    transform: rotateY(180deg);

}

.fa-times-circle {
    color: red;
}

.results {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}

.results-result {
    font-size: 26px;
}

.modal-window {
    padding: 5px 0px 15px 0px;
    display: flex;
    flex-wrap: wrap;
    position: absolute;
    min-height: 350px;
    width: 674px;
    background-color: rgba(255, 255, 255, 1);
    justify-content: space-around;
    left: 50%;
    top: 50%;
    transform: translate(-337px, -175px);
}


.w100 {
    width: 100%;
    text-align: right;
}

.close-modal {
    color: black;
    font-size: 25px;
    margin-right: 30px;
    cursor: pointer;

}

.modal-btn {
    margin-top: 10px;
}

</style>
