<script>
import ImageItem from '@/components/DvcAI/images/image-item';

export default {
    components: {
        ImageItem
    },
    props: {
        images: {
            type: Array,
            default: function () {
                return [];
            },
        },
        updating: {
            type: Boolean,
        },
    },
}
</script>
<template>

    <div v-if="images && images.length > 0">

      <div class="row">
        <div class="col-12">
          <div class="bg-white list-head-text">
            <div class="row align-items-center">
                <span class="col-6 col-md-1"><!--占空用的，为了让镜像名称和下面的内容对其--></span>
                <span class="col-6 col-md-2">镜像名称</span>
                <span class="col-md-2 d-none d-md-block">类型</span>
                <span class="col-6 col-md-2">类库</span>
                <span class="col-md-2 d-none d-md-block">用户</span>
                <span class="col-md-1 text-center d-none d-md-block">创建时间</span>
                <span class="col-md-2 text-center d-none d-md-block">更新时间</span>
            </div>
          </div>
        </div>
      </div>

      <div class="row">
        <div class="col-12">
          <ImageItem v-for="item in images" :key="item.id" :image="item"/>
        </div>
      </div>

    </div>

    <div v-else-if="images.length === 0 && !updating" class="text-center text-secondary mt-4">
      暂无镜像
    </div>

</template>
