<script>
    export default ({
        name: 'MenuItem',
        // props: {
        //     simpleMenu: {
        //         name: 'AnimalCrossingNewHorizon',
        //         image: {source: 'https://assets.nintendo.com/image/upload/c_fill,f_auto,q_auto,w_1200/v1/ncom/en_US/dlc/switch-dlc/animal-crossing-new-horizons-dlc/individual/animal-crossing-new-horizons-happy-home-paradise/image', alt: 'ACNH_image'},
        //         inStock: 'yes',
        //         quantity: 12
        //     }
        // },
        props: [],
        // data() {
        //     return {
        //         simpleMenu: [
        //             // { name: 'lol'}
        //             // { name: String },
        //             // { image: [{ source: String }, { alt: String }] },
        //             // { inStock: String },
        //             // { quantity: Number }
                    
        //             // { name: 'Animal Crossing New Horizon' },
        //             // { image: [{ source: 'https://assets.nintendo.com/image/upload/c_fill,f_auto,q_auto,w_1200/v1/ncom/en_US/dlc/switch-dlc/animal-crossing-new-horizons-dlc/individual/animal-crossing-new-horizons-happy-home-paradise/image' }, { alt: 'ACNH_image' }] },
        //             // { inStock: 'yes' },
        //             // { quantity: 12 }
        //         ]                   
        //     }
        // },

        // created() {
        //     console.log(this.simpleMenu)
        // }
})
</script>

<template>
    <section class="menu">
		<h2>Menu</h2>

		<div v-for="item in simpleMenu" :key="item.name" class="menu-item">
			<img
				class="menu-item__image"
				:src="item.image.source"
				:alt="item.image.alt"
			/>
			<div>
				<h3>{{ item.name }}</h3>
				<p v-if="item.inStock">En stock</p>
				<p v-else>En rupture de stock</p>
				<div>
					<label for="add-item-quantity"
						>Quantité : {{ item.quantity }}</label
					>
					<input
						v-model.number="item.quantity"
						id="add-item-quantity"
						type="number"
					/>
					<button @click="addToShoppingCart(item.quantity)">
					Ajouter au panier d'achat
					</button>
				</div>
			</div>
		</div>
	</section>
</template>