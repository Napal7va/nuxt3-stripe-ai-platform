<template>
    <div class="flex items-center p-4">
        <!-- MobileSidee -->
        <div class="flex w-full justify-end">
            <DropdownMenu as-child>
                <DropdownMenuTrigger>
                    <Button variant="outline">
                    <Icon name="lucide:circle-user"/>
                </Button>
                </DropdownMenuTrigger>
                <DropdownMenuContent align="end" class="w-72 left-[100px]">
                    <DropdownMenuLabel>My Account</DropdownMenuLabel>
                    <DropdownMenuSeparator />
                    <div class="w-full flex items-center p-2 pl-3">
                    <Avata>
                        <Ava
                    </Avata>
                    </div>
                    <DropdownMenuItem>Profile</DropdownMenuItem>
                    <DropdownMenuItem>Billing</DropdownMenuItem>
                    <DropdownMenuItem>Team</DropdownMenuItem>
                    <DropdownMenuItem>Subscription</DropdownMenuItem>
                </DropdownMenuContent>
            </DropdownMenu>
        </div>
    </div>
</template>

<script setup lang="ts">
const user = useSupabaseUser()
</script>

<style scoped>

</style>