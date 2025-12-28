<template>
    <div
        class="notification"
        :class="notificationClass"
        v-if="isActive"
        @click="onClick"
    >
        <div class="notification__icon">
            <img
                :src="notificationImage"
                alt=""
            >
        </div>
        <div class="notification__info">
            <slot></slot>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'BaseNotification',
        props: [
            "text", 'type', 'isActive'
        ],
        data() {
            return {
            }
        },
        computed: {
            notificationClass() {
                return 'notification--' + this.type;
            },
            notificationImage() {
                return 'icon-' + this.type + '.svg';
            }
        },
        methods: {
            onClick() {
                this.$emit('clickOnNotification')
            }
        }
    }
</script>

<style>
    .notification {
        display: flex;
        gap: 20px;
        padding: 20px 20px 16px;
        border-radius: 8px;
        max-width: 400px;
    }

    .notification--danger {
        background-color: #FFF8F8;
        border: 1px solid #F85640;
    }

    .notification--warning {
        background-color: #FFF8EF;
        border: 1px solid #FBA63C;
    }

    .notification--success {
        background-color: #DCF3EB;
        border: 1px solid #34A770;
    }

    .notification--info {
        background-color: #E1F2FC;
        border: 1px solid #08A0F7;
    }

    .notification__icon {
        width: 28px;
        height: 28px;
        flex-shrink: 0;
    }

    .notification__info {
        display: flex;
        flex-direction: column;
        gap: 4px;
    }

    .notification__info h3 {
        font-size: 13px;
        font-weight: 600;
    }

    .notification__info p {
        font-size: 11px;
    }

    .notification--danger h3 {
        color: #F85640;
    }

    .notification--danger p {
        color: #79170A;
    }

    .notification--warning h3 {
        color: #E18109;
    }

    .notification--warning p {
        color: #BC741A;
    }

    .notification--success h3 {
        color: #13854E;
    }

    .notification--success p {
        color: #10673E;
    }

    .notification--info h3 {
        color: #08A0F7;
    }

    .notification--info p {
        color: #3387B7;
    }
</style>