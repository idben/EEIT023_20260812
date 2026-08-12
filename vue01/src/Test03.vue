<script setup></script>

<template>
    <div class="card">
        <!-- header 插槽 -->
        <header>
            <slot name="header"></slot>
        </header>
        <!-- 主要內容 (default) -->
        <main>
            <slot></slot>
        </main>
        <!-- footer 插槽 -->
        <footer>
            <slot name="footer"></slot>
        </footer>
    </div>
</template>

<style scoped>
.card {
    border-radius: 10px;
    overflow: hidden;
    border: 2px solid #043e8b;
}

header {
    background-color: #096beb;
    color: #ffffff;
    padding: 12px;
}

footer {
    background-color: #e6e6e6;
    padding: 8px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
}

main {
    padding: 4px;
}
</style>