cmake_minimum_required(VERSION 3.10)
project(ctrlr)

add_library(ctrlr STATIC)

set(SOURCES_CORE
	Source/Core/CtrlrFontManager.cpp
	Source/Core/CtrlrFontManager.h
	Source/Core/CtrlrIDManager.cpp
	Source/Core/CtrlrIDManager.h
	Source/Core/CtrlrIDs.h
	Source/Core/CtrlrInlineUtilitiesGUI.h
	Source/Core/CtrlrLog.cpp
	Source/Core/CtrlrLog.h
	Source/Core/CtrlrMacros.h
	Source/Core/CtrlrMainPage.h
	Source/Core/CtrlrProperties.cpp
	Source/Core/CtrlrProperties.h
	Source/Core/CtrlrRevision.h
	Source/Core/CtrlrRevision.template
	Source/Core/CtrlrSysexProcessor.cpp
	Source/Core/CtrlrSysexProcessor.h
	Source/Core/CtrlrSysexProcessorOwned.cpp
	Source/Core/CtrlrSysexProcessorOwned.h
	Source/Core/CtrlrSysexToken.cpp
	Source/Core/CtrlrSysexToken.h
	Source/Core/CtrlrUtilities.cpp
	Source/Core/CtrlrUtilities.h
	Source/Core/CtrlrUtilitiesGUI.cpp
	Source/Core/CtrlrUtilitiesGUI.h
	Source/Core/dxtrans.h
#	Source/Core/stdafx.cpp
	Source/Core/stdafx.h
#	Source/Core/stdafx_luabind.cpp
	Source/Core/stdafx_luabind.h
)

set(SOURCES_CORE_MANAGER
	Source/Core/CtrlrManager/CtrlrManager.cpp
	Source/Core/CtrlrManager/CtrlrManager.h
	Source/Core/CtrlrManager/CtrlrManagerInstance.cpp
	Source/Core/CtrlrManager/CtrlrManagerVst.cpp
	Source/Core/CtrlrManager/CtrlrManagerVst.h
)

set(SOURCES_CORE_MODULATOR
	Source/Core/CtrlrModulator/CtrlrModulator.cpp
	Source/Core/CtrlrModulator/CtrlrModulator.h
	Source/Core/CtrlrModulator/CtrlrModulatorProcessor.cpp
	Source/Core/CtrlrModulator/CtrlrModulatorProcessor.h
)

set(SOURCES_CORE_PANEL
	Source/Core/CtrlrPanel/CtrlrEvaluationScopes.cpp
	Source/Core/CtrlrPanel/CtrlrEvaluationScopes.h
	Source/Core/CtrlrPanel/CtrlrPanel.cpp
	Source/Core/CtrlrPanel/CtrlrPanel.h
	Source/Core/CtrlrPanel/CtrlrPanelFileOperations.cpp
	Source/Core/CtrlrPanel/CtrlrPanelMIDIInputThread.cpp
	Source/Core/CtrlrPanel/CtrlrPanelMIDIInputThread.h
	Source/Core/CtrlrPanel/CtrlrPanelMIDISnapshot.cpp
	Source/Core/CtrlrPanel/CtrlrPanelMIDISnapshot.h
	Source/Core/CtrlrPanel/CtrlrPanelProcessor.cpp
	Source/Core/CtrlrPanel/CtrlrPanelProcessor.h
	Source/Core/CtrlrPanel/CtrlrPanelResource.cpp
	Source/Core/CtrlrPanel/CtrlrPanelResource.h
	Source/Core/CtrlrPanel/CtrlrPanelResourceManager.cpp
	Source/Core/CtrlrPanel/CtrlrPanelResourceManager.h
	Source/Core/CtrlrPanel/CtrlrPanelSchemeMigration.cpp
	Source/Core/CtrlrPanel/CtrlrPanelSchemeMigration.h
	Source/Core/CtrlrPanel/CtrlrPanelUndoManager.cpp
	Source/Core/CtrlrPanel/CtrlrPanelUndoManager.h
)

set(SOURCES_CORE_STANDALONEWRAPPER
	Source/Core/StandaloneWrapper/CtrlrStandaloneApplication.cpp
	Source/Core/StandaloneWrapper/CtrlrStandaloneWindow.cpp
	Source/Core/StandaloneWrapper/CtrlrStandaloneWindow.h
)

set(SOURCES_LUA
	Source/Lua/CtrlrLuaAudioConverter.cpp
	Source/Lua/CtrlrLuaAudioConverter.h
	Source/Lua/CtrlrLuaConverters.h
	Source/Lua/CtrlrLuaDebugger.cpp
	Source/Lua/CtrlrLuaDebugger.h
	Source/Lua/CtrlrLuaManager.cpp
	Source/Lua/CtrlrLuaManager.h
	Source/Lua/CtrlrLuaMultiTimer.h
	Source/Lua/CtrlrLuaObject.cpp
	Source/Lua/CtrlrLuaObject.h
	Source/Lua/CtrlrLuaObjectWrapper.cpp
	Source/Lua/CtrlrLuaObjectWrapper.h
	Source/Lua/CtrlrLuaPanelCanvasLayer.cpp
	Source/Lua/CtrlrLuaUtils.cpp
	Source/Lua/CtrlrLuaUtils.h
)

set(SOURCES_LUA_DEPRECATED
	Source/Lua/Deprecated/CtrlrLuaBigInteger.cpp
	Source/Lua/Deprecated/CtrlrLuaBigInteger.h
	Source/Lua/Deprecated/CtrlrLuaComponentAnimator.cpp
	Source/Lua/Deprecated/CtrlrLuaComponentAnimator.h
	Source/Lua/Deprecated/CtrlrLuaFile.cpp
	Source/Lua/Deprecated/CtrlrLuaFile.h
	Source/Lua/Deprecated/CtrlrLuaMemoryBlock.cpp
	Source/Lua/Deprecated/CtrlrLuaMemoryBlock.h
	Source/Lua/Deprecated/CtrlrLuaRectangle.cpp
	Source/Lua/Deprecated/CtrlrLuaRectangle.h
)

set(SOURCES_LUA_JUCECLASSES
	Source/Lua/JuceClasses/LAffineTransform.h
	Source/Lua/JuceClasses/LAlertWindow.h
	Source/Lua/JuceClasses/LAsyncUpdater.h
	Source/Lua/JuceClasses/LAttributedString.h
	Source/Lua/JuceClasses/LAudio.cpp
	Source/Lua/JuceClasses/LAudioFile.h
	Source/Lua/JuceClasses/LAudioFormat.h
	Source/Lua/JuceClasses/LAudioPlayHead.h
	Source/Lua/JuceClasses/LAudioSampleBuffer.h
	Source/Lua/JuceClasses/LAudioThumbnail.h
	Source/Lua/JuceClasses/LBigInteger.h
	Source/Lua/JuceClasses/LBorderSize.h
	Source/Lua/JuceClasses/LBubbleMessageComponent.h
	Source/Lua/JuceClasses/LButton.h
	Source/Lua/JuceClasses/LColour.h
	Source/Lua/JuceClasses/LColourGradient.h
	Source/Lua/JuceClasses/LComboBox.h
	Source/Lua/JuceClasses/LComponent.h
	Source/Lua/JuceClasses/LComponentPeer.h
	Source/Lua/JuceClasses/LComponents.cpp
	Source/Lua/JuceClasses/LCore.cpp
	Source/Lua/JuceClasses/LDrawable.h
	Source/Lua/JuceClasses/LExpression.h
	Source/Lua/JuceClasses/LFile.h
	Source/Lua/JuceClasses/LFileListComponent.h
	Source/Lua/JuceClasses/LFileTreeComponent.h
	Source/Lua/JuceClasses/LFont.h
	Source/Lua/JuceClasses/LGlobalFunctions.h
	Source/Lua/JuceClasses/LGlyphArrangement.h
	Source/Lua/JuceClasses/LGraphics.cpp
	Source/Lua/JuceClasses/LGraphics.h
	Source/Lua/JuceClasses/LImage.h
	Source/Lua/JuceClasses/LInputStream.h
	Source/Lua/JuceClasses/LJuce.cpp
	Source/Lua/JuceClasses/LJuce.h
	Source/Lua/JuceClasses/LJustification.h
	Source/Lua/JuceClasses/LKeyPress.h
	Source/Lua/JuceClasses/LLabel.h
	Source/Lua/JuceClasses/LLine.h
	Source/Lua/JuceClasses/LLookAndFeel.h
	Source/Lua/JuceClasses/LMemory.cpp
	Source/Lua/JuceClasses/LMemoryBlock.h
	Source/Lua/JuceClasses/LMemoryInputStream.h
	Source/Lua/JuceClasses/LMidiBuffer.h
	Source/Lua/JuceClasses/LMidiKeyboardComponent.h
	Source/Lua/JuceClasses/LMidiMessage.h
	Source/Lua/JuceClasses/LModifierKeys.h
	Source/Lua/JuceClasses/LMouseCursor.h
	Source/Lua/JuceClasses/LMouseEvent.h
	Source/Lua/JuceClasses/LPath.h
	Source/Lua/JuceClasses/LPoint.h
	Source/Lua/JuceClasses/LPopupMenu.h
	Source/Lua/JuceClasses/LRandom.h
	Source/Lua/JuceClasses/LRange.h
	Source/Lua/JuceClasses/LRectangle.h
	Source/Lua/JuceClasses/LRelativeCoordinate.h
	Source/Lua/JuceClasses/LResult.h
	Source/Lua/JuceClasses/LSlider.h
	Source/Lua/JuceClasses/LSparseSet.h
	Source/Lua/JuceClasses/LString.h
	Source/Lua/JuceClasses/LTextButton.h
	Source/Lua/JuceClasses/LTextEditor.h
	Source/Lua/JuceClasses/LThread.h
	Source/Lua/JuceClasses/LThreadWithProgressWindow.h
	Source/Lua/JuceClasses/LTime.h
	Source/Lua/JuceClasses/LTimer.h
	Source/Lua/JuceClasses/LToggleButton.h
	Source/Lua/JuceClasses/LTypeface.h
	Source/Lua/JuceClasses/LURL.h
	Source/Lua/JuceClasses/LValue.h
	Source/Lua/JuceClasses/LValueTree.h
	Source/Lua/JuceClasses/LXmlElement.h
	Source/Lua/JuceClasses/LZipFile.h
)

set(SOURCES_LUA_METHODS
	Source/Lua/Methods/CtrlrLuaMethod.cpp
	Source/Lua/Methods/CtrlrLuaMethod.h
	Source/Lua/Methods/CtrlrLuaMethodManager.cpp
	Source/Lua/Methods/CtrlrLuaMethodManager.h
	Source/Lua/Methods/CtrlrLuaMethodManagerCalls.cpp
)

set(SOURCES_MIDI
	Source/MIDI/CtrlrMIDILibrary/CtrlrMIDILibrary.h
	Source/MIDI/CtrlrMIDIDevice.cpp
	Source/MIDI/CtrlrMIDIDevice.h
	Source/MIDI/CtrlrMIDIDeviceManager.cpp
	Source/MIDI/CtrlrMIDIDeviceManager.h
	Source/MIDI/CtrlrMIDIFilter.cpp
	Source/MIDI/CtrlrMIDIFilter.h
	Source/MIDI/CtrlrMidiInputComparator.cpp
	Source/MIDI/CtrlrMidiInputComparator.h
	Source/MIDI/CtrlrMidiInputComparatorMulti.cpp
	Source/MIDI/CtrlrMidiInputComparatorMulti.h
	Source/MIDI/CtrlrMidiInputComparatorSingle.cpp
	Source/MIDI/CtrlrMidiInputComparatorSingle.h
	Source/MIDI/CtrlrMidiInputComparatorTypes.h
	Source/MIDI/CtrlrMidiMessage.cpp
	Source/MIDI/CtrlrMidiMessage.h
	Source/MIDI/CtrlrMidiMessageEx.cpp
	Source/MIDI/CtrlrMidiMessageEx.h
	Source/MIDI/CtrlrOwnedMidiMessage.cpp
	Source/MIDI/CtrlrOwnedMidiMessage.h
)

set(SOURCES_NATIVE
	Source/Native/CtrlrGeneric.h
	Source/Native/CtrlrNative.cpp
	Source/Native/CtrlrNative.h
)

if(MSVC)
	set(SOURCES_NATIVE_PLATFORM	Source/Native/CtrlrWindows.cpp Source/Native/CtrlrWindows.h)
elseif(APPLE)
	set(SOURCES_NATIVE_PLATFORM	Source/Native/CtrlrMac.cpp Source/Native/CtrlrMac.h)
else()
	set(SOURCES_NATIVE_PLATFORM	Source/Native/CtrlrLinux.cpp Source/Native/CtrlrLinux.h)
endif()

set(SOURCES_PLUGIN
	Source/Plugin/CtrlrProcessor.cpp
	Source/Plugin/CtrlrProcessor.h
	Source/Plugin/CtrlrProcessorEditorForLive.cpp
	Source/Plugin/CtrlrProcessorEditorForLive.h
)

set(SOURCES_UICOMPONENTS
	Source/UIComponents/CtrlrAbout.cpp
	Source/UIComponents/CtrlrAbout.h
	Source/UIComponents/CtrlrComponentSelection.cpp
	Source/UIComponents/CtrlrComponentSelection.h
	Source/UIComponents/CtrlrLogViewer.cpp
	Source/UIComponents/CtrlrLogViewer.h
	Source/UIComponents/CtrlrTextEditor.cpp
	Source/UIComponents/CtrlrTextEditor.h
	Source/UIComponents/CtrlrValueMap.cpp
	Source/UIComponents/CtrlrValueMap.h
	Source/UIComponents/CtrlrValueTreeEditor.cpp
	Source/UIComponents/CtrlrValueTreeEditor.h
)

set(SOURCES_UICOMPONENTS_APPLICATIONWINDOW
	Source/UIComponents/CtrlrApplicationWindow/CtrlrDocumentPanel.cpp
	Source/UIComponents/CtrlrApplicationWindow/CtrlrDocumentPanel.h
	Source/UIComponents/CtrlrApplicationWindow/CtrlrEditor.cpp
	Source/UIComponents/CtrlrApplicationWindow/CtrlrEditor.h
	Source/UIComponents/CtrlrApplicationWindow/CtrlrEditorApplicationCommands.cpp
	Source/UIComponents/CtrlrApplicationWindow/CtrlrEditorApplicationCommandsHandlers.cpp
	Source/UIComponents/CtrlrApplicationWindow/CtrlrEditorApplicationCommandsMenus.cpp
	Source/UIComponents/CtrlrApplicationWindow/CtrlrSettings.cpp
	Source/UIComponents/CtrlrApplicationWindow/CtrlrSettings.h
)

set(SOURCES_UICOMPONENTS_CTRLRCOMPONENTS
	Source/UIComponents/CtrlrComponents/Statics/CtrlrArrow.cpp
	Source/UIComponents/CtrlrComponents/Statics/CtrlrArrow.h
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrButton.cpp
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrButton.h
	Source/UIComponents/CtrlrComponents/CtrlrCombo.cpp
	Source/UIComponents/CtrlrComponents/CtrlrCombo.h
	Source/UIComponents/CtrlrComponents/CtrlrComponent.cpp
	Source/UIComponents/CtrlrComponents/CtrlrComponent.h
	Source/UIComponents/CtrlrComponents/CtrlrComponentLuaRegistration.cpp
	Source/UIComponents/CtrlrComponents/CtrlrComponentTypeManager.cpp
	Source/UIComponents/CtrlrComponents/CtrlrComponentTypeManager.h
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrCustomButtonInternal.cpp
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrCustomButtonInternal.h
	Source/UIComponents/CtrlrComponents/CtrlrCustomComponent.cpp
	Source/UIComponents/CtrlrComponents/CtrlrCustomComponent.h
	Source/UIComponents/CtrlrComponents/Specials/CtrlrFileListBox.cpp
	Source/UIComponents/CtrlrComponents/Specials/CtrlrFileListBox.h
	Source/UIComponents/CtrlrComponents/CtrlrFilmStripPainter.cpp
	Source/UIComponents/CtrlrComponents/CtrlrFilmStripPainter.h
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrFixedImageSlider.cpp
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrFixedImageSlider.h
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrFixedSlider.cpp
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrFixedSlider.h
	Source/UIComponents/CtrlrComponents/Groups/CtrlrGroup.cpp
	Source/UIComponents/CtrlrComponents/Groups/CtrlrGroup.h
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrHyperlink.cpp
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrHyperlink.h
	Source/UIComponents/CtrlrComponents/Labels/CtrlrImage.cpp
	Source/UIComponents/CtrlrComponents/Labels/CtrlrImage.h
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrImageButton.cpp
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrImageButton.h
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrImageSlider.cpp
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrImageSlider.h
	Source/UIComponents/CtrlrComponents/Labels/CtrlrLabel.cpp
	Source/UIComponents/CtrlrComponents/Labels/CtrlrLabel.h
	Source/UIComponents/CtrlrComponents/Labels/CtrlrLCDLabel.cpp
	Source/UIComponents/CtrlrComponents/Labels/CtrlrLCDLabel.h
	Source/UIComponents/CtrlrComponents/Specials/CtrlrListBox.cpp
	Source/UIComponents/CtrlrComponents/Specials/CtrlrListBox.h
	Source/UIComponents/CtrlrComponents/Specials/CtrlrMidiKeyboard.cpp
	Source/UIComponents/CtrlrComponents/Specials/CtrlrMidiKeyboard.h
	Source/UIComponents/CtrlrComponents/Specials/CtrlrProgressBar.cpp
	Source/UIComponents/CtrlrComponents/Specials/CtrlrProgressBar.h
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrSlider.cpp
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrSlider.h
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrSliderInternal.cpp
	Source/UIComponents/CtrlrComponents/Sliders/CtrlrSliderInternal.h
	Source/UIComponents/CtrlrComponents/Groups/CtrlrTabsComponent.cpp
	Source/UIComponents/CtrlrComponents/Groups/CtrlrTabsComponent.h
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrToggleButton.cpp
	Source/UIComponents/CtrlrComponents/Buttons/CtrlrToggleButton.h
	Source/UIComponents/CtrlrComponents/Specials/CtrlrWaveform.cpp
	Source/UIComponents/CtrlrComponents/Specials/CtrlrWaveform.h
	Source/UIComponents/CtrlrComponents/Specials/CtrlrXYModulator.cpp
	Source/UIComponents/CtrlrComponents/Specials/CtrlrXYModulator.h
	Source/UIComponents/CtrlrComponents/Specials/CtrlrXYSurface.cpp
	Source/UIComponents/CtrlrComponents/Specials/CtrlrXYSurface.h
)

set(SOURCES_UICOMPONENTS_CTRLRLUA
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaCodeTokeniser.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaCodeTokeniser.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaCodeTokeniserFunctions.h
	Source/UIComponents/CtrlrLua/CtrlrLuaConsole.cpp
	Source/UIComponents/CtrlrLua/CtrlrLuaConsole.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodCodeEditor.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodCodeEditor.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodCodeEditorSettings.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodCodeEditorSettings.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerControls.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerControls.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerInfo.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerInfo.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerPrompt.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerPrompt.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerStackTrace.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerStackTrace.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerVars.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodDebuggerVars.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodEditArea.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodEditArea.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodEditor.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodEditor.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodEditorConsole.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodEditorConsole.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodEditorTabs.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodEditorTabs.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodFind.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrLuaMethodFind.h
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrMethodEditorTabCloseButton.cpp
	Source/UIComponents/CtrlrLua/MethodEditor/CtrlrMethodEditorTabCloseButton.h
)

set(SOURCES_UICOMPONENTS_CTRLRMIDI
	Source/UIComponents/CtrlrMIDI/CtrlrMIDIBuffer.cpp
	Source/UIComponents/CtrlrMIDI/CtrlrMIDIBuffer.h
#	Source/UIComponents/CtrlrMIDI/CtrlrMIDIBufferEditor.cpp			does not compile
#	Source/UIComponents/CtrlrMIDI/CtrlrMIDIBufferEditor.h
	Source/UIComponents/CtrlrMIDI/CtrlrMIDICalculator.cpp
	Source/UIComponents/CtrlrMIDI/CtrlrMIDICalculator.h
	Source/UIComponents/CtrlrMIDI/CtrlrMIDIMon.cpp
	Source/UIComponents/CtrlrMIDI/CtrlrMIDIMon.h
	Source/UIComponents/CtrlrMIDI/CtrlrMIDISettingsDevices.cpp
	Source/UIComponents/CtrlrMIDI/CtrlrMIDISettingsDevices.h
	Source/UIComponents/CtrlrMIDI/CtrlrMIDISettingsDialog.cpp
	Source/UIComponents/CtrlrMIDI/CtrlrMIDISettingsDialog.h
	Source/UIComponents/CtrlrMIDI/CtrlrMIDISettingsRouting.cpp
	Source/UIComponents/CtrlrMIDI/CtrlrMIDISettingsRouting.h
)

set(SOURCES_UICOMPONENTS_CTRLRPANEL
	Source/UIComponents/CtrlrPanel/CtrlrPanelCanvas.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelCanvas.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelCanvasHandlers.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelCanvasLayer.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelCanvasLayer.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelCanvasLayers.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelComponentProperties.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelComponentProperties.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelEditor.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelEditor.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelFindProperty.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelFindProperty.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelLayerList.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelLayerList.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelLayerListItem.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelLayerListItem.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelModulatorList.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelModulatorList.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelModulatorListTree.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelModulatorListTree.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelProperties.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelProperties.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelResourceEditor.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelResourceEditor.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelUtilities.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelUtilities.h
	Source/UIComponents/CtrlrPanel/CtrlrPanelViewport.cpp
	Source/UIComponents/CtrlrPanel/CtrlrPanelViewport.h
	Source/UIComponents/CtrlrPanel/CtrlrViewport.cpp
	Source/UIComponents/CtrlrPanel/CtrlrViewport.h
)

set(SOURCES_UICOMPONENTS_CTRLRPROPERTYEDITORS
	Source/UIComponents/CtrlrPropertyEditors/CtrlrPropertyComponent.cpp
	Source/UIComponents/CtrlrPropertyEditors/CtrlrPropertyComponent.h
)

set(SOURCES_UICOMPONENTS_CTRLRWINDOWMANAGERS
	Source/UIComponents/CtrlrWindowManagers/CtrlrChildWindow.cpp
	Source/UIComponents/CtrlrWindowManagers/CtrlrChildWindow.h
	Source/UIComponents/CtrlrWindowManagers/CtrlrChildWindowContainer.cpp
	Source/UIComponents/CtrlrWindowManagers/CtrlrChildWindowContainer.h
	Source/UIComponents/CtrlrWindowManagers/CtrlrChildWindowContent.cpp
	Source/UIComponents/CtrlrWindowManagers/CtrlrChildWindowContent.h
	Source/UIComponents/CtrlrWindowManagers/CtrlrDialogWindow.cpp
	Source/UIComponents/CtrlrWindowManagers/CtrlrDialogWindow.h
	Source/UIComponents/CtrlrWindowManagers/CtrlrManagerWindowManager.cpp
	Source/UIComponents/CtrlrWindowManagers/CtrlrManagerWindowManager.h
	Source/UIComponents/CtrlrWindowManagers/CtrlrPanelWindowManager.cpp
	Source/UIComponents/CtrlrWindowManagers/CtrlrPanelWindowManager.h
)

target_sources(ctrlr PRIVATE 
	${SOURCES_CORE} 
	${SOURCES_CORE_MANAGER} 
	${SOURCES_CORE_MODULATOR}
	${SOURCES_CORE_PANEL}
#	${SOURCES_CORE_STANDALONEWRAPPER}
	${SOURCES_LUA}
	${SOURCES_LUA_DEPRECATED}
	${SOURCES_LUA_JUCECLASSES}
	${SOURCES_LUA_METHODS}
	${SOURCES_MIDI}
	${SOURCES_NATIVE}
	${SOURCES_NATIVE_PLATFORM}
	${SOURCES_PLUGIN}
	${SOURCES_UICOMPONENTS}
	${SOURCES_UICOMPONENTS_APPLICATIONWINDOW}
	${SOURCES_UICOMPONENTS_CTRLRCOMPONENTS}
	${SOURCES_UICOMPONENTS_CTRLRLUA}
	${SOURCES_UICOMPONENTS_CTRLRMIDI}
	${SOURCES_UICOMPONENTS_CTRLRPANEL}
	${SOURCES_UICOMPONENTS_CTRLRPROPERTYEDITORS}
	${SOURCES_UICOMPONENTS_CTRLRWINDOWMANAGERS}
)

source_group("source\\Core" FILES ${SOURCES_CORE})
source_group("source\\Core\\Manager" FILES ${SOURCES_CORE_MANAGER})
source_group("source\\Core\\Modulator" FILES ${SOURCES_CORE_MODULATOR})
source_group("source\\Core\\Panel" FILES ${SOURCES_CORE_PANEL})
source_group("source\\Core\\StandaloneWrapper" FILES ${SOURCES_CORE_STANDALONEWRAPPER})

source_group("source\\Lua" FILES ${SOURCES_LUA})
source_group("source\\Lua\\Deprecated" FILES ${SOURCES_LUA_DEPRECATED})
source_group("source\\Lua\\JuceClasses" FILES ${SOURCES_LUA_JUCECLASSES})
source_group("source\\Lua\\Methods" FILES ${SOURCES_LUA_METHODS})

source_group("source\\MIDI" FILES ${SOURCES_MIDI})

source_group("source\\Native" FILES ${SOURCES_NATIVE} ${SOURCES_NATIVE_PLATFORM})

source_group("source\\Plugin" FILES ${SOURCES_PLUGIN})

source_group("source\\UIComponents" FILES ${SOURCES_UICOMPONENTS})
source_group("source\\UIComponents\\ApplicationWindow" FILES ${SOURCES_UICOMPONENTS_APPLICATIONWINDOW})
source_group("source\\UIComponents\\Components" FILES ${SOURCES_UICOMPONENTS_CTRLRCOMPONENTS})
source_group("source\\UIComponents\\Lua" FILES ${SOURCES_UICOMPONENTS_CTRLRLUA})
source_group("source\\UIComponents\\MIDI" FILES ${SOURCES_UICOMPONENTS_CTRLRMIDI})
source_group("source\\UIComponents\\Panel" FILES ${SOURCES_UICOMPONENTS_CTRLRPANEL})
source_group("source\\UIComponents\\PropertyEditors" FILES ${SOURCES_UICOMPONENTS_CTRLRPROPERTYEDITORS})
source_group("source\\UIComponents\\WindowManagers" FILES ${SOURCES_UICOMPONENTS_CTRLRWINDOWMANAGERS})

target_include_directories(ctrlr PRIVATE 
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/Misc/lua/include"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/Misc/luabind"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/Misc/include"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/Misc"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/Core"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/MIDI"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/Lua"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/UIComponents"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source/Plugin"
	"${CMAKE_CURRENT_SOURCE_DIR}/Source"
	"${CMAKE_CURRENT_SOURCE_DIR}/JuceLibraryCode"
	"${CMAKE_CURRENT_SOURCE_DIR}/JUCE/modules"
)
