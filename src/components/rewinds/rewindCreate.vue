<template>
  <div>
    <div class="row">
      <div class="col">
        <p>Tel adedi:</p>
      </div>
      <div class="col">
        <label for>tel çapı</label>
      </div>
      <div class="col">
        <p>Tel kesidi:</p>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <input v-model="actualWire[0].quantity" type="number" step="1" class="form-control" />
      </div>
      <div class="col">
        <input v-model="actualWire[0].guage" type="number" step="0.01" class="form-control" />
      </div>
      <div class="col">
        <p>{{sectioncalc(actualWire[0].guage)}} mm</p>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <input v-model="actualWire[1].quantity" type="number" class="form-control" />
      </div>
      <div class="col">
        <input v-model="actualWire[1].guage" type="number" step="0.01" class="form-control" />
      </div>
      <div class="col">
        <p>{{sectioncalc(actualWire[1].guage)}} mm</p>
      </div>
    </div>

    <div class="row">
      <table class="table table-sm">
        <thead>
          <th scope="col"></th>
          <th scope="col">Gerilim</th>
          <th scope="col">Frekans</th>
          <th scope="col">Akım</th>
          <th scope="col">Spir sayısı</th>
          <th scope="col">tel tplm kesidi</th>
        </thead>
        <tbody>
          <tr>
            <th scope="row">Asıl</th>
            <td><input v-model="actualVoltage" type="text" class="form-control" /></td>
            <td><input v-model="actualFrequency" type="text" class="form-control" /></td>
            <td><input v-model="actualCurrent" type="text" class="form-control" /></td>
            <td><input v-model="actualNumberOfTurns" type="text" class="form-control" /></td>
            <td>{{totalsectioncalc(0)}}</td>
          </tr>
          <tr>
            <th scope="row">Sarılacak</th>
            <td><input v-model="newVoltage" type="text" class="form-control" /></td>
            <td><input v-model="newFrequency" type="text" class="form-control" /></td>
            <td>{{(actualVoltage/newVoltage)*actualCurrent}}</td>
            <td>{{Math.ceil(actualNumberOfTurns * newVoltage/actualVoltage)}}</td>
            <td>{{newWireSection}}</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="row">
      <div class="col">
        <input v-model="newWire[0].quantity" type="text" class="form-control" />
      </div>
      <div class="col">
        <input v-model="newWire[0].guage" type="text" class="form-control" />
      </div>
      <div class="col">
        <p>{{sectioncalc(newWire[0].guage)}} mm</p>
      </div>
      <div class="col">
        <p>Hesaplanan kesit</p>
      </div>

    </div>
    <div class="row">
      <div class="col">
        <input v-model="newWire[1].quantity" type="text" class="form-control" />
      </div>
      <div class="col">
        <input v-model="newWire[1].guage" type="text" class="form-control" />
      </div>
      <div class="col">
        <p>{{sectioncalc(newWire[1].guage)}} mm</p>
      </div>
      <div class="col " v-bind:class=" wireSectionValid() ? 'bg-success' : 'bg-danger' ">
        <p >{{totalsectioncalc(1)}}</p>
      </div>
    </div>


      <button @click="newWireCalc()" class="btn btn-primary">Tahmini tel hesapla</button>
      <div class="row" v-if="result.length>0" >
        <div class="col">#</div>
        <div class="col">Adet 1</div>
        <div class="col">Tel çapı 1</div>
        <div class="col">Adet 2</div>
        <div class="col">Tel çapı 1</div>
        <div class="col">Toplam kesidi</div>
        <div class="col">Uyum oranı</div>
      </div>
      <div class="row" v-for="(result,index) in result" v-bind:key="index" >
        <div class="col"> <input v-bind="selectedradio" type="radio" name="radio" id="" @click="chooseWire(index)">  {{index+1}}</div>
        <div class="col">{{result[0].quantity}}</div>
        <div class="col">{{result[0].guage}}</div>
        <div class="col">{{result.length > 1 ? result[1].quantity : '0'}}</div>
        <div class="col">{{result.length > 1 ? result[1].guage : '0'}}</div>
        <div class="col">{{result.length > 1 ? (result[0].section + result[1].section).toFixed(4) : result[0].section.toFixed(4)}}</div>
        <div class="col">{{result.length > 1 ? result[1].guage : '0'}}</div>
        
      </div>


  </div>
</template>

<script>
export default {
  name: "rewindCreate",
  data: function() {
    return {
      customer: "Dalgakıran",
      serialNumber: "0987654321",
      materialNumber: "1234567890",
      productionDate: "01-01-2017",
      motor: {
        brand: "WEG",
        series: "W22",
        type: "Standard",
        power: 55,
        speed: 1000,
        voltage: 400,
        frequency: 400,
        effeciency: "IE2",
        frame: 225,
        pole: 6
      },
      actualWire: [
        {
          quantity: 2,
          guage: 1.18,
          section: 0
        },
        {
          quantity: 3,
          guage: 1,
          section: 0
        }
      ],
      actualVoltage: 400,
      actualCurrent: 1,
      actualFrequency: 50,
      actualNumberOfTurns: 15,
      actualWireSection: 15,
      newVoltage: 400,
      newCurrent: 1,
      newFrequency: 84,
      newNumberOfTurns: 15,
      
      newWire: [
        {
          quantity: 2,
          guage: 0.5,
          section: 0
        },
        {
          quantity: 2,
          guage: 0.5,
          section: 0
        }
      ],
      wires:[0.5,0.55,0.6,0.65,0.7,0.75,0.8,0.85,0.90,0.95,1,1.05,1.1,1.15,1.2,1.25,1.3,1.35,1.4],
      result: [],
      selectedradio: false
      

    
    
    
    };
  },
  methods:{
      chooseWire : function(index){
        if(this.result[index].length > 1){
          this.newWire = this.result[index].concat();
        }
        else {
          Object.assign(this.newWire[0],this.result[index][0]);
          Object.assign(this.newWire[1],{ quantity: 0,guage: 0,section: 0});
        }
      },
      sectioncalc: function(diameter){
          let result = Math.PI * Math.pow( diameter/2 , 2) ;
          return result.toFixed(3);
      },
      totalsectioncalc: function(actual){
          let result = 0;
          if(actual==0){
              result= this.actualWire[0].quantity*this.sectioncalc(this.actualWire[0].guage) + this.actualWire[1].quantity*this.sectioncalc(this.actualWire[1].guage)
          }
          else {
              result= this.newWire[0].quantity*this.sectioncalc(this.newWire[0].guage) + this.newWire[1].quantity*this.sectioncalc(this.newWire[1].guage)
          }
          result =  result.toFixed(4);
          return result;
      },
      wireSectionValid: function(){
        if(Math.abs(this.totalsectioncalc(1) / this.newWireSection -1 ) <= 0.015 ){
          return true
        }
        else{
          return false
        }
        
      },
      newWireCalc: function() {
        let avr,biggertwo,smallertwo,fullarr,quantity;
        let result = Array();
        //calculate average of two used wires
        avr = (Number(this.actualWire[0].guage) + Number(this.actualWire[1].guage)) / 2;
        //getting the bigger two wire guages
        biggertwo = this.wires.filter(function(wire) {
          return wire > avr; 
        });
        biggertwo = biggertwo.slice(0,2);
        // getting the smaller two wire guages
        smallertwo = this.wires.filter(function(wire) {
          return wire <= avr; 
        });
        smallertwo = smallertwo.reverse().slice(0,2);
        // merging and sorting both arrays
        fullarr = smallertwo.concat(biggertwo).sort();
        
        // calculate possible wire using only one wire 
        for(let wire of fullarr){

          quantity = Math.ceil(this.newWireSection / this.sectioncalc(wire));

          if(Math.abs(quantity * this.sectioncalc(wire) / this.newWireSection - 1) <= 0.015 ){
            result.push([{'quantity':quantity , 'guage': wire , 'section':quantity * this.sectioncalc(wire)}])
          }
          else if(Math.abs((quantity-1)*this.sectioncalc(wire) / this.newWireSection - 1) <= 0.015){
            result.push([{'quantity':quantity-1 , 'guage': wire , 'section':(quantity-1) * this.sectioncalc(wire)}])
          }
          else if(Math.abs((quantity+1)*this.sectioncalc(wire) / this.newWireSection - 1) <= 0.015){
            result.push([{'quantity':quantity+1 , 'guage': wire , 'section':(quantity+1) * this.sectioncalc(wire)}])
          }
        }
        
        //calculate possible rtwo wire compination 
        let ttlsect,newsectpercent,i,j,k;
        for(i=1; i <= 20; i++ ){
          for (j= 1; j < 20 ; j++) {
            for(k= 0; k < 3 ; k++){
              ttlsect = i * this.sectioncalc(fullarr[k]) + j * this.sectioncalc(fullarr[k+1]);
              newsectpercent = Math.abs(ttlsect / this.newWireSection -1 );
              if (newsectpercent <= 0.015 ) {
                result.push([
                  {'quantity':i , 'guage': fullarr[k] , 'section':i * this.sectioncalc(fullarr[k])},
                  {'quantity':j , 'guage': fullarr[k+1]  , 'section':j * this.sectioncalc(fullarr[k+1])}
                ])
              }
            }
          }
        }
        this.selectedradio= false;
        this.result=result;

      }
  },
  computed:{
    newWireSection: function(){
      let result = this.totalsectioncalc(0) * this.actualVoltage/this.newVoltage;
      result = result.toFixed(4)
     return result;
    },
    

  },

};
</script>

<style>
</style>
