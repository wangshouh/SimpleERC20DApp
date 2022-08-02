<template>
    <div class="card" v-if="metamaskInfo.installBool">
        <div class="card-content">
            <div class="content" v-if="metamaskInfo.ethAccount">
                <table class="table">
                    <tr>
                        <td>ChainID</td>
                        <td>{{ metamaskInfo.chainId  }}</td>
                    </tr>
                    <tr>
                        <td>Address</td>
                        <td>{{ metamaskInfo.ethAccount.slice(0, 15) }}</td>
                    </tr>
                </table>
            </div>
            <div class="content has-text-centered" v-else>
                <button class="button is-medium is-info is-light" @click="connectWallent()">Connect to MetaMask</button>
            </div>
        </div>
    </div>
    <div class="card" v-else>
        <div class="card-image">
            <figure class="image">
                <img src="https://img.wongssh.cf/file/wongsshblog/MetaMask_Fox.svg" alt="Placeholder image">
            </figure>
        </div>
        <div class="card-content is-size-5">
            <p>You not install MetaMask.</p>
            <p>Go to <a href="https://metamask.io/download/" target="_blank">install</a> </p>
        </div>
    </div>

</template>

<style>
</style>

<script setup>
import { reactive, onMounted, ref } from 'vue'
import { ethers } from "ethers";

const metamaskInfo = reactive({
    install: false,
    localUpdateTime: null,
    ethAccount: null
});

onMounted(() => {
    if (typeof window.ethereum !== 'undefined') {
        metamaskInfo.installBool = true;
        metamaskInfo.ethAccount = localStorage.getItem("ethAccount");
        metamaskInfo.chainId = window.ethereum.chainId 
    }
});

function connectWallent() {
    window.ethereum.request({ method: 'eth_requestAccounts' }).then(
        accounts => {
            metamaskInfo.ethAccount = accounts[0];
            localStorage.setItem("ethAccount", metamaskInfo.ethAccount);
            console.log(metamaskInfo.ethAccount);
        }
    )
}
</script>