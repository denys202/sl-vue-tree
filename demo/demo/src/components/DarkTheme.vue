<template>
    <h2> Sl-vue-tree - custom dark theme and events handlers</h2>

    <div class="last-event row">
        Last event: {{ lastEvent }}
    </div>

    <div class="row">
        <div class="tree-container">
            <sl-vue-tree
                v-model="nodes"
                ref="slVueTree"
                :allow-multiselect="false"
                @select="nodeSelected"
                @drop="nodeDropped"
                @toggle="nodeToggled"
                @nodecontextmenu="showContextMenu"
                :could-be-child="couldBeChild"
            >

<!--                <template slot="title" slot-scope="{ node }">-->
<!--          <span class="item-icon">-->
<!--            <i class="fa fa-file" v-if="node.isLeaf"></i>-->
<!--            <i class="fa fa-folder" v-if="!node.isLeaf"></i>-->
<!--          </span>-->

<!--                    {{ node.title }}-->
<!--                </template>-->


<!--                <template slot="toggle" slot-scope="{ node }">-->
<!--          <span v-if="!node.isLeaf">-->
<!--            <i v-if="node.isExpanded" class="fa fa-chevron-down"></i>-->
<!--            <i v-if="!node.isExpanded" class="fa fa-chevron-right"></i>-->
<!--          </span>-->
<!--                </template>-->


<!--                <template slot="sidebar" slot-scope="{ node }">-->
<!--          <span class="visible-icon" @click="event => toggleVisibility(event, node)">-->
<!--            <i v-if="!node.data || node.data.visible !== false" class="fa fa-eye"></i>-->
<!--            <i v-if="node.data && node.data.visible === false" class="fa fa-eye-slash"></i>-->
<!--          </span>-->
<!--                </template>-->


<!--                <template slot="draginfo" slot-scope="{ nodes, cursorPosition}">-->
<!--                    {{ couldBeChildInfo(nodes, cursorPosition) }}-->
<!--                </template>-->

            </sl-vue-tree>
        </div>
    </div>
</template>

<script>
import SlVueTree from "../../../../src/sl-vue-tree.vue";
export default {
  name: "DarkTheme",
  components: {
    SlVueTree,
  },
  data: function () {
    return {
      nodes: [{
        "title": "headertop", "isLeaf": false, "isSelectable": false, "isDraggable": false, "data": {
          "active": true,
          "links": {
            "add": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_parent=2&addprotothemeeditor_molecule&id_root=2",
            "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=2&updateprotothemeeditor_molecule",
            "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=2&deleteprotothemeeditor_molecule",
            "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=2&viewprotothemeeditor_molecule",
            "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=2&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
          },
          "icon": "/modules/protothemeeditor/views/img/types/container.svg",
          "label": "Container",
          "type": "container",
          "id": 2,
          "idParent": null,
          "childrenTypes": ["row"]
        }, "isExpanded": true, "children": [{
          "title": "row_3", "isLeaf": false, "isSelectable": true, "isDraggable": true, "data": {
            "active": true,
            "links": {
              "add": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_parent=3&addprotothemeeditor_molecule&id_root=2",
              "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=3&updateprotothemeeditor_molecule",
              "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=3&deleteprotothemeeditor_molecule",
              "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=3&viewprotothemeeditor_molecule",
              "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=3&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
            },
            "icon": "/modules/protothemeeditor/views/img/types/row.svg",
            "label": "Ligne",
            "type": "row",
            "id": 3,
            "idParent": 2,
            "childrenTypes": ["col"]
          }, "isExpanded": true, "children": [{
            "title": "12/12 (taille normale)", "isLeaf": false, "isSelectable": true, "isDraggable": true, "data": {
              "active": true,
              "links": {
                "add": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_parent=4&addprotothemeeditor_molecule&id_root=2",
                "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=4&updateprotothemeeditor_molecule",
                "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=4&deleteprotothemeeditor_molecule",
                "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=4&viewprotothemeeditor_molecule",
                "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=4&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
              },
              "icon": "/modules/protothemeeditor/views/img/types/default.svg",
              "label": "Colonne",
              "type": "col",
              "id": 4,
              "idParent": 3,
              "childrenTypes": ["accordeon", "alert", "banner", "carousel", "container", "html_content", "dropdown", "funnel_link", "image", "interstitial", "link", "row", "blog_post_list", "category_list", "link_list", "manufacturer_list", "custom_list", "product_list", "megamenu", "mobile_menu", "category_miniature", "product_miniature", "modal", "tabjs", "separator", "title", "topic_link", "video", "widget", "common_widget"]
            }, "isExpanded": true, "children": [{
              "title": "widget_8",
              "isLeaf": true,
              "isSelectable": true,
              "isDraggable": true,
              "data": {
                "active": true,
                "links": {
                  "add": null,
                  "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=8&updateprotothemeeditor_molecule",
                  "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=8&deleteprotothemeeditor_molecule",
                  "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=8&viewprotothemeeditor_molecule",
                  "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=8&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
                },
                "icon": "/modules/protothemeeditor/views/img/types/widget.svg",
                "label": "Widget PrestaShop",
                "type": "widget",
                "id": 8,
                "idParent": 4,
                "childrenTypes": []
              }
            }, {
              "title": "container_5", "isLeaf": false, "isSelectable": true, "isDraggable": true, "data": {
                "active": true,
                "links": {
                  "add": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_parent=5&addprotothemeeditor_molecule&id_root=2",
                  "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=5&updateprotothemeeditor_molecule",
                  "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=5&deleteprotothemeeditor_molecule",
                  "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=5&viewprotothemeeditor_molecule",
                  "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=5&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
                },
                "icon": "/modules/protothemeeditor/views/img/types/container.svg",
                "label": "Container",
                "type": "container",
                "id": 5,
                "idParent": 4,
                "childrenTypes": ["row"]
              }, "isExpanded": true, "children": [{
                "title": "row_6", "isLeaf": false, "isSelectable": true, "isDraggable": true, "data": {
                  "active": true,
                  "links": {
                    "add": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_parent=6&addprotothemeeditor_molecule&id_root=2",
                    "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=6&updateprotothemeeditor_molecule",
                    "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=6&deleteprotothemeeditor_molecule",
                    "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=6&viewprotothemeeditor_molecule",
                    "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=6&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
                  },
                  "icon": "/modules/protothemeeditor/views/img/types/row.svg",
                  "label": "Ligne",
                  "type": "row",
                  "id": 6,
                  "idParent": 5,
                  "childrenTypes": ["col"]
                }, "isExpanded": true, "children": [{
                  "title": "12/12 (taille normale)", "isLeaf": false, "isSelectable": true, "isDraggable": true, "data": {
                    "active": true,
                    "links": {
                      "add": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_parent=7&addprotothemeeditor_molecule&id_root=2",
                      "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=7&updateprotothemeeditor_molecule",
                      "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=7&deleteprotothemeeditor_molecule",
                      "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=7&viewprotothemeeditor_molecule",
                      "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=7&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
                    },
                    "icon": "/modules/protothemeeditor/views/img/types/default.svg",
                    "label": "Colonne",
                    "type": "col",
                    "id": 7,
                    "idParent": 6,
                    "childrenTypes": ["accordeon", "alert", "banner", "carousel", "container", "html_content", "dropdown", "funnel_link", "image", "interstitial", "link", "row", "blog_post_list", "category_list", "link_list", "manufacturer_list", "custom_list", "product_list", "megamenu", "mobile_menu", "category_miniature", "product_miniature", "modal", "tabjs", "separator", "title", "topic_link", "video", "widget", "common_widget"]
                  }, "isExpanded": true, "children": [{
                    "title": "widget_9",
                    "isLeaf": true,
                    "isSelectable": true,
                    "isDraggable": true,
                    "data": {
                      "active": true,
                      "links": {
                        "add": null,
                        "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=9&updateprotothemeeditor_molecule",
                        "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=9&deleteprotothemeeditor_molecule",
                        "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=9&viewprotothemeeditor_molecule",
                        "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=9&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
                      },
                      "icon": "/modules/protothemeeditor/views/img/types/widget.svg",
                      "label": "Widget PrestaShop",
                      "type": "widget",
                      "id": 9,
                      "idParent": 7,
                      "childrenTypes": []
                    }
                  }, {
                    "title": "alert_37",
                    "isLeaf": true,
                    "isSelectable": true,
                    "isDraggable": true,
                    "data": {
                      "active": true,
                      "links": {
                        "add": null,
                        "update": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=37&updateprotothemeeditor_molecule",
                        "delete": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=37&deleteprotothemeeditor_molecule",
                        "view": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&token=2df320a8d017cd4713eda359e69d6ed9&id_molecule=37&viewprotothemeeditor_molecule",
                        "status": "https://prestashop178.denys.tot/bb/index.php?controller=AdminProtothemeeditorLocationMolecule&id_molecule=37&ajax=1&statusprotothemeeditor_molecule=1&action=statusprotothemeeditor_molecule&token=2df320a8d017cd4713eda359e69d6ed9"
                      },
                      "icon": "/modules/protothemeeditor/views/img/types/alert.svg",
                      "label": "Alerte",
                      "type": "alert",
                      "id": 37,
                      "idParent": 7,
                      "childrenTypes": []
                    }
                  }]
                }]
              }]
            }]
          }]
        }]
      }],
      contextMenuIsVisible: false,
      lastEvent: 'No last event',
      selectedNodesTitle: '',
    }
  },

  mounted() {
    // expose instance to the global namespace
    window.slVueTree = this.$refs.slVueTree;
  },

  methods: {
    couldBeChild(selectedNode, cursorPosition) {
      return this.couldBeChildInfo([selectedNode], cursorPosition);
    },
    couldBeChildInfo(nodes, cursorPosition) {
      if (nodes.length === 0 || !cursorPosition) {
        return '';
      }

      const tree = this.$refs.slVueTree;
      const currentTarget = nodes[0];
      const canBeReplaced = !tree.checkNodeIsParent(currentTarget, cursorPosition.node);
      const positionRule = !(cursorPosition.node.level === 1 && (['after', 'before'].includes(cursorPosition.placement)))
      console.log(canBeReplaced);
      console.log(positionRule);
      return canBeReplaced && positionRule;
    },

    toggleVisibility: function (event, node) {
      const slVueTree = this.$refs.slVueTree;
      event.stopPropagation();
      const visible = !node.data || node.data.visible !== false;
      slVueTree.updateNode(node.path, {data: {visible: !visible}});
      this.lastEvent = `Node ${node.title} is ${visible ? 'visible' : 'invisible'} now`;
    },

    nodeSelected(nodes, event) {
      this.selectedNodesTitle = nodes.map(node => node.title).join(', ');
      this.lastEvent = `Select nodes: ${this.selectedNodesTitle}`;
    },

    nodeToggled(node, event) {
      this.lastEvent = `Node ${node.title} is ${node.isExpanded ? 'expanded' : 'collapsed'}`;
    },

    nodeDropped(nodes, position, event) {
      this.lastEvent = `Nodes: ${nodes.map(node => node.title).join(', ')} are dropped ${position.placement} ${position.node.title}`;
    },

    showContextMenu(node, event) {
      event.preventDefault();
      this.contextMenuIsVisible = true;
      const $contextMenu = this.$refs.contextmenu;
      $contextMenu.style.left = event.clientX + 'px';
      $contextMenu.style.top = event.clientY + 'px';
    },

    removeNode() {
      this.contextMenuIsVisible = false;
      const $slVueTree = this.$refs.slVueTree;
      const paths = $slVueTree.getSelected().map(node => node.path);
      $slVueTree.remove(paths);
    }
  }
}
</script>

<style lang="scss">
@import "../../../../dist/sl-vue-tree-minimal.css";

body {
    background: #050d12;
    font-family: Arial;
    color: rgba(255, 255, 255, 0.5);
}

a {
    color: #bbb;
}

.row {
    display: flex;
    margin-bottom: 10px;
}

.contextmenu {
    position: absolute;
    background-color: white;
    color: black;
    border-radius: 2px;
    cursor: pointer;
}

.contextmenu > div {
    padding: 10px;
}

.contextmenu > div:hover {
    background-color: rgba(100, 100, 255, 0.5);
}


.last-event {
    color: white;
    background-color: rgba(100, 100, 255, 0.5);
    padding: 10px;
    border-radius: 2px;
}

.tree-container {
    flex-grow: 1;
}

.sl-vue-tree.sl-vue-tree-root {
    flex-grow: 1;
    overflow-x: hidden;
    overflow-y: auto;
    height: 300px;
}

.json-preview {
    flex-grow: 1;
    margin-left: 10px;
    background-color: #13242d;
    border: 1px solid black;
    padding: 10px;
}

.item-icon {
    display: inline-block;
    text-align: left;
    width: 20px;
}

</style>