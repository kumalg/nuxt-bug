<template>
<div>
    INDEX {{ data.foo }}
</div>
</template>

<script>
export default {
    async setup() {
        const { data } = await useAsyncData(() => {
            return {
                foo: 'bar'
            }
        })

        useHead({
            title: data.value.foo
        })

        return {
            data
        }
    }
}
</script>