<template>
    <div>
        <pet-list title="Male" :value="pets.male"></pet-list>
        <pet-list title="Female" :value="pets.female"></pet-list>
    </div>
</template>

<script>
import axios from 'axios'
import PetList from './PetList'

export default {

    name: 'Pets',

    components: {
        PetList
    },

    props: {
        src: {
            type: String,
            required: true
        }
    },

    data () {
        return {
            pets: {
                male: [],
                female: []
            }
        }
    },

    created () {
        axios.get(this.src)
            .then(resp => {
                let r = resp.data.reduce((accumulator, person) => {
                    if (person.pets) {
                        accumulator[person.gender.toLowerCase()].push(
                            ...person.pets
                                .filter(pet => pet.type === 'Cat')
                                .map(pet => pet.name)
                        );
                    }
                    return accumulator;
                }, { male: [], female: []});
                this.pets.male = r.male.sort();
                this.pets.female = r.female.sort();
            });
    }
}
</script>

