*****************code for robot.glb *************************************


import React, { useRef } from 'react'
import { useGLTF, useAnimations } from '@react-three/drei'

export function Model(props) {
  const group = useRef()
  const { nodes, materials, animations } = useGLTF(‘/robot.glb')
  const { actions } = useAnimations(animations, group)
  return (
    <group ref={group} {...props} dispose={null}>
      <group name="Sketchfab_Scene">
        <group name="Sketchfab_model" rotation={[-Math.PI / 2, 0, 0]}>
          <group
            name="160e2a757fac4082bf52e1068b9784a1fbx"
            rotation={[Math.PI / 2, 0, 0]}
            scale={0.01}>
            <group name="Object_2">
              <group name="RootNode">
                <group name="Cylinder005" />
                <group name="Armature" rotation={[-Math.PI / 2, 0, 0]} scale={100}>
                  <group name="Object_6">
                    <primitive object={nodes._rootJoint} />
                    <skinnedMesh
                      name="Object_9"
                      geometry={nodes.Object_9.geometry}
                      material={materials.uv_checker_material_uv_grid_2048x2048}
                      skeleton={nodes.Object_9.skeleton}
                    />
                    <skinnedMesh
                      name="Object_529"
                      geometry={nodes.Object_529.geometry}
                      material={materials.uv_checker_material_uv_grid_2048x2048}
                      skeleton={nodes.Object_529.skeleton}
                    />
                    <group name="Object_8" />
                    <group name="Object_528" />
                  </group>
                </group>
                <group name="Cylinder115" />
              </group>
            </group>
          </group>
        </group>
      </group>
    </group>
  )
}

useGLTF.preload(‘/robot.glb')