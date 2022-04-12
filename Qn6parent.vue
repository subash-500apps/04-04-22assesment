<template>
    <div>
        <p>
        </p>
    </div>
</template>
<script>
import React, { Component } from 'react';

import helllU from '../components/Qn6.vue';
export default{
name:summU,
components:{
    
    name:helllU
}

}

const Humbug = {
    name: 'Humbug',
    level: 5,
    hp: 20
}

class GameMgr extends Component {
    constructor(props) {
        super(props);
    }

    render() {
        return(
            <div>
                <Zombie name={"Geek"} level={5} hp={21}></Zombie>
                <Zombie {...Humbug}></Zombie>
            </div>
        )
    }
}

export default GameMgr;
</script>