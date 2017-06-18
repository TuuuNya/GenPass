<template>
    <div id="genpass">
        <el-row>
            <el-col :span="4" :offset="10">
                <el-form ref="form" :model="form">
                    <el-form-item label="密钥">
                        <el-input v-model="form.key"></el-input>
                    </el-form-item>
                    <el-form-item label="域名">
                        <el-input v-model="form.domain"></el-input>
                    </el-form-item>
                    <el-form-item label="结果">
                        <el-input v-model="form.output"></el-input>
                    </el-form-item>
                    <el-form-item>
                        <el-button type="primary" v-on:click="generatePassword">生成密码</el-button>
                    </el-form-item>
                </el-form>
            </el-col>
        </el-row>
    </div>
</template>

<script>
import md5 from 'md5'

export default{
    name: 'genpass',
    data() {
    	return {
    		form: {
    			key: '',
                domain: '',
                output: ''
            }
        }
    },
    methods: {
    	generatePassword: function(){
    		if(this.form.key == '' || this.form.domain == ''){
                this.$message('请输入密钥和域名！');
            }else{
                let password = md5(this.form.key + this.form.domain);
                this.form.output = password.substring(0,15);
            }
        }
    }
}
</script>

<style>
#genpass h1{
  color: red;
}
</style>
