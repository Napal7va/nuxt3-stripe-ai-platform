<template>
    <div class="flex items-center p-4">
        <!-- MobileSidee -->
        <MobileSidebar/>
        <div class="flex w-full justify-end">
            <DropdownMenu as-child>
                <DropdownMenuTrigger>
                    <Button variant="outline">
                    <Icon name="lucide:circle-user"/>
                </Button>
                </DropdownMenuTrigger>
                <DropdownMenuContent align="end" class="w-72 left-[100px]">
                    <DropdownMenuLabel>My Account</DropdownMenuLabel>
                    
                    <div class="w-full flex items-center p-2 pl-3">
                    <Avatar class="mr-2">
                        <AvatarImage 
                        v-if="user?.user_metadata.avatar_url"
                        :src="user.user_metadata.avatar_url"
                        >
                        <AvatarCallback>
                            {{ user.email?.charAt(0).toUpperCase }}
                            {{ user.email?.charAt(1).toUpperCase }}
                        </AvatarCallback>
                        </AvatarImage>
                    </Avatar>
                    <div>
                        <div class="font-bold">
                            {{ user?.user_metadata.full_name }}
                        </div>
                        <div class="text-sm">
                            {{ user?.email }}
                        </div>
                    </div>
                    </div>
                    <DropdownMenuSeparator />
                    <DropdownMenuItem @click="logout">
                        <Icon class="mr-2 h-4 w-4" name="heroicons:arrow-left-on-rectangle"/>
                        <span class="ml-2">
                            logout
                        </span>
                    </DropdownMenuItem>
                </DropdownMenuContent>
            </DropdownMenu>
        </div>
    </div>
</template>

<script setup lang="ts">
import MobileSidebar from './MobileSidebar.vue';
const user = useSupabaseUser();
const supabaseClient = useSupabaseClient();

const logout = async () => {
    await supabaseClient.auth.signOut();
    navigateTo('/auth')
};
</script>

<style scoped>

</style>