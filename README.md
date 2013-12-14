#ItemStacks
#==========

#This is a code for itemstacks in Eclipse/bukkit

package me.YourName.tutorial;

import java.util.ArrayList;

import org.bukkit.ChatColor;
import org.bukkit.Material;
import org.bukkit.command.Command;
import org.bukkit.command.CommandSender;
import org.bukkit.entity.Player;
import org.bukkit.inventory.ItemStack;
import org.bukkit.inventory.meta.ItemMeta;
import org.bukkit.plugin.java.JavaPlugin;

public class Tutorial extends JavaPlugin {

        public void onEnable(){
                // Where to register events and more
        }
        
        // Basic Command Setup
        public boolean onCommand(CommandSender sender, Command cmd, String label, String[] a){
                Player player = (Player) sender;
                if(cmd.getName().equalsIgnoreCase("command")){
                        // Add the custom ItemStack to the player's inventory
                        player.getInventory().addItem(wool);
                }
                return false;
        }
        
        ItemStack wool = new ItemStack(Material.WOOL);
        {
        ItemMeta itemmeta = wool.getItemMeta();
        ArrayList<String> im = new ArrayList<String>();
        itemmeta.setDisplayName(ChatColor.GOLD + "Wool");
        im.add(ChatColor.GREEN + "Line 1");
        im.add(ChatColor.RED + "Line 2");
        im.add(ChatColor.YELLOW + "" + ChatColor.BOLD + "Bolded Line");
        itemmeta.setLore(im);
        wool.setItemMeta(itemmeta);
        }
}
