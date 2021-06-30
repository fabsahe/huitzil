<template>
	<div>
		<v-row>
			<v-col cols="4" v-for="item in results" :key="item.id">
				<v-card class="mx-auto" max-width="344" v-on="answerTime ? { click: () => checkAnswer(item.val) } : {}">
					<span class="mul-res">{{ item.val }}</span>
				</v-card>
			</v-col>
					
		</v-row>
		<v-row>
			<v-col cols="2"></v-col>
			<v-col cols="6">
				<vue-card-stack :cards="cards" :stack-width="440" :card-width="380" :card-height="240" :maxVisibleCards="7">
					<template v-slot:card="{ card }">
						<div style="width: 100%; height: 100%;" :style="{ background: card.background }"
						><br><br><span class="mul-txt">{{ card.text }}</span></div>
					</template>

					<template v-slot:nav="{ activeCardIndex, onNext  }">
						<nav class="nav">
							<div class="text-right">
								<v-btn v-on:click="nextCard(activeCardIndex, onNext)" class="teal lighten-2 no-up btn-next" dark>
									Tomar
								</v-btn>
							</div>
						</nav>
					</template>
				</vue-card-stack>
			</v-col>

			<v-col cols=3>
				<v-img
					alt="Pointing1"
					class="shrink mr-2 img-point"
					contain
					src="../assets/pointing1.png"
					transition="scale-transition"
					v-if="!answerTime"
					width="220"></v-img>
				<v-img
					alt="Pointing1"
					class="shrink mr-2 img-point"
					contain
					src="../assets/pointing2.png"
					transition="scale-transition"
					v-if="answerTime"
					width="220"></v-img>
			</v-col>

		</v-row>
	</div>
</template>

<script>
import VueCardStack from "vue-card-stack"
import swal from 'sweetalert'

export default {
	name: "Memorama",

	components: {
		VueCardStack,
	},

	data() {
		return {
			answerTime: false,
			answerVal: -1,
			answersCount: 0,
			results: [ 
				{id: 1, val: 0},
				{id: 2, val: 0},
				{id: 3, val: 0}
			],

			cards: [
				{ background: "#F48FB1", text: "", result: "" },
				{ background: "#EF9A9A", text: "3 x 7", result: 21 },
				{ background: "#CE93D8", text: "4 x 6", result: 24 },
				{ background: "#9FA8DA", text: "5 x 4", result: 20 },
				{ background: "#90CAF9", text: "4 x 8", result: 32 },
				{ background: "#81D4FA", text: "6 x 3", result: 18 },
				{ background: "#80CBC4", text: "7 x 2", result: 14 },
				{ background: "#A5D6A7", text: "8 x 8", result: 64 },
				{ background: "#C5E1A5", text: "9 x 4", result: 36 },	
				{ background: "#FFCC80", text: "5 x 6", result: 30 },
				{ background: "#BCAAA4", text: "6 x 7", result: 42 },				
			],

			cards2: [
				{ background: "#F48FB1", text: "", result: "" },
				{ background: "#EF9A9A", text: "3 x 7", result: 21 },
				{ background: "#CE93D8", text: "4 x 6", result: 24 },
				{ background: "#9FA8DA", text: "5 x 4", result: 20 },
				{ background: "#90CAF9", text: "4 x 8", result: 32 },
				{ background: "#81D4FA", text: "6 x 3", result: 18 },
				{ background: "#80CBC4", text: "7 x 2", result: 14 },
				{ background: "#A5D6A7", text: "8 x 8", result: 64 },
				{ background: "#C5E1A5", text: "9 x 4", result: 36 },	
				{ background: "#FFCC80", text: "5 x 6", result: 30 },
				{ background: "#BCAAA4", text: "6 x 7", result: 42 },				
			],			
		};
	},

	methods: {
		getRandomInt(min, max) {
			return Math.floor(Math.random() * (max - min)) + min;
		},

		nextCard(index, f) {
			if( !this.answerTime ) {
				f()
				if( index!=0 ) {
					this.answerTime = true
					let apos = this.getRandomInt(0,3)
					let ans1 = this.getRandomInt(8,50)
					let ans2 = this.getRandomInt(8,50)
					let ans3 = this.getRandomInt(8,50)

					this.results[0].val = ans1
					this.results[1].val = ans2
					this.results[2].val = ans3

					this.results[apos].val = this.cards2[index].result		
					this.answerVal = this.cards2[index].result
				}
			}
		},

		checkAnswer(val) {
			if( this.answerVal == val ) {
				swal("Muy bien C:", "", "success")
				this.answerTime = false
				this.answersCount++
				if( this.answersCount==6 ) {
					swal("¡Bien! has terminado con esto", "", "success")
				}
			}
			else {
				swal("Te equivocaste :C", "", "error")
			}
		}
	}
}

</script>

<style>
.swal-title {
	font-family: 'Varela Round', sans-serif !important;
}
.swal-button {
	font-family: 'Varela Round', sans-serif !important;
}
.img-point {
	margin:  5rem 0 0 0;
}
.no-up {
  text-transform: none;
}
.btn-next {
	margin-top: -19rem;
}
.mul-txt {
	font-size: 5rem;
	margin:  4rem 0 0 6rem;
	color: #424242;
}
.mul-res {
	font-size: 4rem;
	margin:  1rem 0 1rem 8rem;
}
</style>