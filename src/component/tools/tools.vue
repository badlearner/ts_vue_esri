<template>
    <div class="tools">
        <el-tooltip class="item" effect="light" content="材料包管理" placement="bottom">
            <el-button type="primary" @click="manage" icon="menu"></el-button>
        </el-tooltip>
        <el-tooltip class="item" effect="light" content="打印出图" placement="bottom">
            <el-button type="primary" @click="print" icon="picture"></el-button>
        </el-tooltip>
        <el-tooltip class="item" effect="light" content="宗地" placement="bottom">
            <el-button type="primary" @click="land" icon="d-caret"></el-button>
        </el-tooltip>
        <div class="dialog">
            <el-dialog title="材料包管理" :visible.sync="materialPackageManagement">
                <material-package-management></material-package-management>
            </el-dialog>
            <el-dialog title="打印出图" :visible.sync="printOutPicture">
                <print-out-picture></print-out-picture>
            </el-dialog>
            <el-dialog title="搜索定位" :visible.sync="landDialog" size="tiny">
                <land-search></land-search>
            </el-dialog>
        </div>
    </div>
</template>
<style>
    .tools{position: absolute;width:800px;height:40px;left:50%;top:5px;margin-left:-400px;text-align: center;}
    .dialog{text-align: left;}
</style>
<script>
    import ElDialog from "../../../node_modules/element-ui/packages/dialog/src/component.vue";
    import MaterialPackageManagement from "./materialPackageManagement/materialPackageManagement.vue";
    import PrintOutPicture from "./printOutPicture/printOutPicture.vue";
    import LandSearch from "./landSearch/landSearch.vue";
    export default {
        components: {ElDialog,MaterialPackageManagement,PrintOutPicture,LandSearch},
        data(){
            return {
                materialPackageManagement:false,
                printOutPicture:false,
                landDialog:false
            }
        },
        methods: {
            manage(){
                this.materialPackageManagement=true;
            },
            print(){
                this.printOutPicture=true;
            },
            land(){
                this.landDialog=true;
            }
        }
    }
</script>