<template>
    <div class="resource">
        <el-row>
            <el-col :span="20">
                <h1>资源大厅</h1>
            </el-col>
            <el-col :span="4">
                <el-input placeholder="搜索" class="search">
                    <template v-slot:append>
                        <el-button><el-icon>
                                <Search />
                            </el-icon>搜索</el-button>
                    </template>
                </el-input>
            </el-col>
        </el-row>

        <el-tabs v-model="activeTab">
            <el-tab-pane label="服务" name="service">
                <div class="tabs">
                    <el-row>
                        <el-col :span="2">
                            <p>服务类型：</p>
                        </el-col>
                        <el-col :span="21">
                            <el-radio-group v-model="serviceType" class="options">
                                <el-collapse-transition>
                                    <div v-if="showAllServiceType">
                                        <el-radio-button label="不限"></el-radio-button>
                                        <el-radio-button label="检验检测"></el-radio-button>
                                        <el-radio-button label="研究开发"></el-radio-button>
                                        <el-radio-button label="科技金融"></el-radio-button>
                                        <el-radio-button label="科技咨询"></el-radio-button>
                                        <el-radio-button label="技术转移"></el-radio-button>
                                        <el-radio-button label="知识产权"></el-radio-button>
                                        <el-radio-button label="科学技术普及"></el-radio-button>
                                        <el-radio-button label="综合科技服务"></el-radio-button>
                                        <el-radio-button label="创业孵化"></el-radio-button>
                                    </div>
                                    <div v-else>
                                        <el-radio-button label="不限"></el-radio-button>
                                        <el-radio-button label="检验检测"></el-radio-button>
                                        <el-radio-button label="研究开发"></el-radio-button>
                                        <el-radio-button label="科技金融"></el-radio-button>
                                        <el-radio-button label="科技咨询"></el-radio-button>
                                        <el-radio-button label="技术转移"></el-radio-button>
                                        <el-radio-button label="知识产权"></el-radio-button>
                                        <el-radio-button label="科学技术普及"></el-radio-button>
                                        <el-radio-button label="综合科技服务"></el-radio-button>
                                        <el-radio-button label="创业孵化"></el-radio-button>
                                    </div>
                                </el-collapse-transition>
                            </el-radio-group>
                        </el-col>
                        <el-col :span="1">
                            <el-button type="text" @click="showAllServiceType = !showAllServiceType">{{ showAllServiceType
                                ? '收起' :
                                '展开' }}</el-button>
                        </el-col>
                    </el-row>
                    <el-divider border-style="dashed" />
                    <el-row>
                        <el-col :span="2">
                            <p>技术领域：</p>
                        </el-col>
                        <el-col :span="21">
                            <el-radio-group v-model="technologyField" class="options">
                                <el-collapse-transition>
                                    <div v-if="showAllTechnologyField">
                                        <el-radio-button label="不限"></el-radio-button>
                                        <el-radio-button label="现代农业"></el-radio-button>
                                        <el-radio-button label="电子信息"></el-radio-button>
                                        <el-radio-button label="资源与环境"></el-radio-button>
                                        <el-radio-button label="生物与新医药"></el-radio-button>
                                        <el-radio-button label="新材料"></el-radio-button>
                                        <el-radio-button label="高技术服务"></el-radio-button>
                                        <el-radio-button label="航空航天"></el-radio-button>
                                        <el-radio-button label="新能源与节能"></el-radio-button>
                                        <el-radio-button label="建筑业"></el-radio-button>
                                        <el-radio-button label="先进制造与自动化"></el-radio-button>
                                        <el-radio-button label="其他"></el-radio-button>
                                    </div>
                                    <div v-else>
                                        <el-radio-button label="不限"></el-radio-button>
                                        <el-radio-button label="现代农业"></el-radio-button>
                                        <el-radio-button label="电子信息"></el-radio-button>
                                        <el-radio-button label="资源与环境"></el-radio-button>
                                        <el-radio-button label="生物与新医药"></el-radio-button>
                                        <el-radio-button label="新材料"></el-radio-button>
                                        <el-radio-button label="高技术服务"></el-radio-button>
                                        <el-radio-button label="航空航天"></el-radio-button>
                                        <el-radio-button label="新能源与节能"></el-radio-button>
                                        <el-radio-button label="建筑业"></el-radio-button>
                                    </div>
                                </el-collapse-transition>
                            </el-radio-group>
                        </el-col>
                        <el-col :span="1">
                            <el-button type="text" @click="showAllTechnologyField = !showAllTechnologyField">{{
                                showAllTechnologyField
                                ? '收起' :
                                '展开' }}</el-button>
                        </el-col>
                    </el-row>
                    <el-divider border-style="dashed" />
                    <el-row>
                        <el-col :span="2">
                            <p>数据来源：</p>
                        </el-col>
                        <el-col :span="21">
                            <el-radio-group v-model="dataSource" class="options">
                                <el-collapse-transition>
                                    <div v-if="showAllDataSource">
                                        <el-radio-button label="不限"></el-radio-button>
                                        <el-radio-button label="共创云"></el-radio-button>
                                        <el-radio-button label="科惠网"></el-radio-button>
                                        <el-radio-button label="江西省网上常设技术市场"></el-radio-button>
                                        <el-radio-button label="潇湘科技要素大市场"></el-radio-button>
                                    </div>
                                    <div v-else>
                                        <el-radio-button label="不限"></el-radio-button>
                                        <el-radio-button label="共创云"></el-radio-button>
                                        <el-radio-button label="科惠网"></el-radio-button>
                                        <el-radio-button label="江西省网上常设技术市场"></el-radio-button>
                                        <el-radio-button label="潇湘科技要素大市场"></el-radio-button>
                                    </div>
                                </el-collapse-transition>
                            </el-radio-group>
                        </el-col>
                        <el-col :span="1">
                            <el-button type="text" @click="showAllRegions = !showAllRegions">{{ showAllRegions
                                ? '收起' :
                                '展开' }}</el-button>
                        </el-col>
                    </el-row>
                    <el-divider border-style="dashed" />
                    <el-row>
                        <el-col :span="2">
                            <p>地区：</p>
                        </el-col>
                        <el-col :span="21">
                            <el-radio-group v-model="region" class="options">
                                <el-collapse-transition>
                                    <div v-if="showAllRegions">
                                        <el-radio-button label="不限"></el-radio-button>
                                        <el-radio-button label="湖北省"></el-radio-button>
                                        <el-radio-button label="湖南省"></el-radio-button>
                                        <el-radio-button label="江西省"></el-radio-button>
                                        <el-radio-button label="北京市"></el-radio-button>
                                        <el-radio-button label="天津市"></el-radio-button>
                                        <el-radio-button label="河北省"></el-radio-button>
                                        <el-radio-button label="山西省"></el-radio-button>
                                        <el-radio-button label="内蒙古自治区"></el-radio-button>
                                        <el-radio-button label="辽宁省"></el-radio-button>
                                        <el-radio-button label="吉林省"></el-radio-button>
                                        <el-radio-button label="黑龙江省"></el-radio-button>
                                        <el-radio-button label="上海市"></el-radio-button>
                                        <el-radio-button label="江苏省"></el-radio-button>
                                        <el-radio-button label="浙江省"></el-radio-button>
                                        <el-radio-button label="安徽省"></el-radio-button>
                                        <el-radio-button label="福建省"></el-radio-button>
                                        <el-radio-button label="山东省"></el-radio-button>
                                        <el-radio-button label="河南省"></el-radio-button>
                                        <el-radio-button label="广东省"></el-radio-button>
                                        <el-radio-button label="广西壮族自治区"></el-radio-button>
                                        <el-radio-button label="海南省"></el-radio-button>
                                        <el-radio-button label="重庆市"></el-radio-button>
                                        <el-radio-button label="四川省"></el-radio-button>
                                        <el-radio-button label="贵州省"></el-radio-button>
                                        <el-radio-button label="云南省"></el-radio-button>
                                        <el-radio-button label="西藏自治区"></el-radio-button>
                                        <el-radio-button label="陕西省"></el-radio-button>
                                        <el-radio-button label="甘肃省"></el-radio-button>
                                        <el-radio-button label="青海省"></el-radio-button>
                                        <el-radio-button label="宁夏回族自治区"></el-radio-button>
                                        <el-radio-button label="新疆维吾尔自治区"></el-radio-button>
                                        <el-radio-button label="台湾省"></el-radio-button>
                                        <el-radio-button label="香港特别行政区"></el-radio-button>
                                        <el-radio-button label="澳门特别行政区"></el-radio-button>
                                    </div>
                                    <div v-else>
                                        <el-radio-button label="不限"></el-radio-button>
                                        <el-radio-button label="湖北省"></el-radio-button>
                                        <el-radio-button label="湖南省"></el-radio-button>
                                        <el-radio-button label="江西省"></el-radio-button>
                                        <el-radio-button label="北京市"></el-radio-button>
                                        <el-radio-button label="天津市"></el-radio-button>
                                        <el-radio-button label="河北省"></el-radio-button>
                                        <el-radio-button label="山西省"></el-radio-button>
                                        <el-radio-button label="内蒙古自治区"></el-radio-button>
                                        <el-radio-button label="辽宁省"></el-radio-button>
                                        <el-radio-button label="吉林省"></el-radio-button>
                                        <el-radio-button label="黑龙江省"></el-radio-button>
                                        <el-radio-button label="上海市"></el-radio-button>
                                    </div>
                                </el-collapse-transition>
                            </el-radio-group>
                        </el-col>
                        <el-col :span="1">
                            <el-button type="text" @click="showAllRegions = !showAllRegions">{{ showAllRegions
                                ? '收起' :
                                '展开' }}</el-button>
                        </el-col>
                    </el-row>
                    <el-divider border-style="dashed" />
                </div>
            </el-tab-pane>
        </el-tabs>

        <el-table :data="filteredData">
            <el-table-column prop="title" label="服务名称"></el-table-column>
            <el-table-column prop="serviceTypeName" label="服务类型"></el-table-column>
            <el-table-column prop="totalDeal" label="成功成交数"></el-table-column>
            <el-table-column prop="avgScore" label="信用评价"></el-table-column>
        </el-table>
    </div>
</template>
<script lang="ts">
import { computed, defineComponent, ref } from 'vue';

export default defineComponent({
    name: 'SearchView',
    setup() {
        const activeTab = ref('service');
        const serviceType = ref('不限');
        const showAllServiceType = ref(false);
        const technologyField = ref('不限');
        const showAllTechnologyField = ref(false);
        const dataSource = ref('不限');
        const showAllDataSource = ref(false);
        const region = ref('不限');
        const showAllRegions = ref(false);
        const tableData = ref<any[]>([]);

        const getAllData = async () => {
            let pageNum = 1;
            let lastPage = 239;
            do {
                const response = await fetch(`https://service.test.nttcc.com.cn/api/v1/service/list?pageNum=${pageNum}`);
                const data = await response.json();
                tableData.value = [...tableData.value, ...data.data.list];
                pageNum++;
            } while (pageNum <= lastPage);
        };
        getAllData();

        const filteredData = computed(() => {
  return tableData.value.filter((item) => {
    return (
      (region.value === '不限' || item.region === region.value) &&
      (dataSource.value === '不限' || item.dataSource === dataSource.value) &&
      (technologyField.value === '不限' || item.technologyField === technologyField.value) &&
      (serviceType.value === '不限' || item.serviceType === serviceType.value)
    );
  });
});

        return {
            activeTab,
            serviceType,
            showAllServiceType,
            technologyField,
            showAllTechnologyField,
            dataSource,
            showAllDataSource,
            region,
            showAllRegions,
            filteredData
        }
    }
});
</script>
<style scoped>
.resource {
    margin-top: 30px;
    margin-left: 120px;
    margin-right: 120px;
    padding-top: 20px;
    padding-left: 30px;
    padding-right: 30px;
    padding-bottom: 20px;
    box-shadow: 0 0 2px #5d5a5a;
    border-radius: 2px;
    background-color: #ffff;
}

.tabs {
    padding: 20px;
    border: 1px solid;
    border-radius: 2px;
}

.el-divider--horizontal {
    margin: 1px 0;
    background: 0 0;
    border-top: 1px dashed #e8eaec;
}

.search {
    height: 40px;
}

.service-options {
    display: flex;
    flex-wrap: wrap;
    overflow: hidden;
    height: 30px;
}

.service-options .el-radio-button {
    margin-right: 10px;
}
</style>
