<template>
    <button class="btn">
        <slot />
    </button>
    </template>

    <style scoped>
    .btn {
        padding: 12px 22px;
        border-radius: var(--radius);
        border: none;
        background: var(--primary);
        color: white;
        tont-weight: bold;
        cursor: pointer;
    }
</style>