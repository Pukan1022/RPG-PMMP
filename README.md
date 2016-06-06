<?php

namespace Registone;

use pocketmine\plugin\PluginBase;
use pocketmine\event\Listener;
use pocketmine\event\player\PlayerItemHeldEvent;
use pocketmine\entity\Effect;
use pocketmine\event\entity\EntityDamageEvent;
use pocketmine\event\entity\EntityRegainHealthEvent;
use pocketmine\network\Network;
use pocketmine\network\protocol\MobEffectPacket;
use pocketmine\Player;
use pocketmine\utils\TextFormat;

class Registone extends PluginBase implements Listener {
	public function onEnable() {
		$this->getServer ()->getPluginManager ()->registerEvents ( $this, $this );
		$this->getServer()->getLogger()->info(TextFormat::GRAY."
			[Registone]방어석 플러그인이 활성화 되었습니다.");
	}
	public function onHeld(PlayerItemHeldEvent $event) {
		$id = $event->getItem ()->getId ();
		$player=$event->getPlayer();
		if ($id == 318){
		$effect = Effect::getEffect(11);
		$effect->setDuration (10 * 20);
		$effect->setAmplifier (0);
		$player->addEffect($effect);
	}
	}
}
?>
